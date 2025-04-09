
## How to start ( Start from the step 29 if you're already have the detection model )

1. First of all, create python virtual environment using command:


```bash
python -m venv env
```


2. Start the environment by typing

```bash
env\Scripts\activate.bat
```


3. Install all of the package using this command (Ignore it if there is any error with the torch installation):


```bash
pip install -r requirements.txt
```

4. Upload your images in `/data/detection/raw/` directory

5. Run the `/module/detection/preprocessing.ipynb`

6. Copy all the file that generated in `/data/detection/preprocessed` into https://roboflow.com/

7. If you don't have an account, create first!

8. Just click continue for all of the administration process

9. Create new workspace

10. Go to the `Project` section

11. Create new Project with 'Object Detection' type

12. Upload all images from `/data/detection/preprocessed`

13. Go to the `Annotate` section

14. Click `Annotate Images` from `Unsigned` section

15. Select the `Manual Labeling` one

16. Invite team members or `Assign to myself` if you're doing self-project

17. Click each image and follow the instruction to annotate (make sure each image is labelled as spark plug condition (e.g. ideal, burned, etc))

18. If annotation process is done, then go to `Dataset` section

19. Click on `New Dataset Version` button

20. Select the source image

21. Split the data into 3 categories (train, test, valid), by clicking the `Rebalance` button

22. Balance the data, I would recommend you using 70:10:20 method (70% training, 10% validation, 20% testing)

23. Just continue until generating

24. Click `Download Dataset` button

25. Select the `COCO` format and then download it as a zip

26. Extract the zip file into `/data/detection/labeled`

27. For CUDA usage, run this command:
```bash
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124
```

28. Run the `/module/detection/training.ipynb` file, and then it should produce trained model in `/model/detection.pth` file

29. To get the accuracy of the model or testing the model, run the `/module/detection/testing.ipynb`