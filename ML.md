## deployment

![[Pasted image 20250915151024.png]]

concept drift and data drift
* detect and manage changes

software engineering issues
* realtime or batch
* cloud vs. edge/browser
* compute resources (cpu/gpu/memory)
* latency, throughput (qps)
* logging
* security and privacy

monitoring
* brainstorm the things that could go wrong
* brainstorm a few statistic/metrics that will detect the problem
* it is ok to use many metrics initially and gradually remove the ones you find not useful
___
* software metrics
* input metrics
* output metrics
*how quickly do they change (user data usually slower drift/b2b can shift fast)
___
* set thresholds for alarms
* adapt metrics and thresholds over time

ml pipline
example => user data - user profile - recommendation system - product recommendation


```python
import os
import cv2
import cvlib as cv
from cvlib.object_detection import draw_bbox
import io
import uvicorn
import numpy as np
import nest_asyncio
from enum import Enum
from fastapi import FastAPI, UploadFile, File, HTTPException
from fastapi.responses import StreamingResponse

dir_name = "images_uploaded"
if not os.path.exists(dir_name):
    os.mkdir(dir_name)

# Assign an instance of the FastAPI class to the variable "app".
# You will interact with your api using this instance.
app = FastAPI(title='Deploying a ML Model with FastAPI')

# By using @app.get("/") you are allowing the GET method to work for the / endpoint.
@app.get("/")
def home():
    return "Congratulations! Your API is working as expected. Now head over to <your_server>/docs"

# This endpoint handles all the logic necessary for the object detection to work.
# It requires the desired model and the image in which to perform object detection.
@app.post("/predict")
def prediction(file: UploadFile = File(...)):

    # 1. VALIDATE INPUT FILE

    filename = file.filename
    fileExtension = filename.split(".")[-1] in ("jpg", "jpeg", "png")
    if not fileExtension:
        raise HTTPException(status_code=415, detail="Unsupported file provided.")

    # 2. TRANSFORM RAW IMAGE INTO CV2 image

    # Read image as a stream of bytes
    image_stream = io.BytesIO(file.file.read())

    # Start the stream from the beginning (position zero)
    image_stream.seek(0)

    # Write the stream of bytes into a numpy array
    file_bytes = np.asarray(bytearray(image_stream.read()), dtype=np.uint8)

    # Decode the numpy array as an image
    image = cv2.imdecode(file_bytes, cv2.IMREAD_COLOR)

    # 3. RUN OBJECT DETECTION MODEL

    # Run object detection
    bbox, label, conf = cv.detect_common_objects(image, model='yolov3-tiny')

    # Create image that includes bounding boxes and labels
    output_image = draw_bbox(image, bbox, label, conf)

    # Save it in a folder within the server
    cv2.imwrite(f'{dir_name}/{filename}', output_image)

    # 4. STREAM THE RESPONSE BACK TO THE CLIENT

    # Open the saved image for reading in binary mode
    file_image = open(f'{dir_name}/{filename}', mode="rb")

    # Return the image as a stream specifying media type
    return StreamingResponse(file_image, media_type="image/jpeg")
```

## select a model

![[Pasted image 20250915144642.png]]

AI system = Code + Data

model + hyperparameters + data => training => error analysis

1. doing well on training set (avg. training error)
2. doing well on dev/test set
3. doing well on business metrics/

___

performance on disproportionally important examples
performance on key slices of the dataset
rare classes

establish a baseline

