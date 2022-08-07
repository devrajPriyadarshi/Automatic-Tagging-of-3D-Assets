
# Automatic Tagging of 3D Assets and 2D Images in a Directory

<!-- ### **Purpose:**
A 3D artist would often download many 3D assets for his use. This projects aims to automate the process of identifying and classifying such models in a directory. -->


### **Model:**
We are using a light-weight model of [PointNet](http://stanford.edu/~rqi/pointnet/), a close implementation of the [Keras Tutorial](https://keras.io/examples/vision/pointnet/) with added features, such as: saving and loading a model, Converting OBJ and PLY files into model compatible input etc.

### **Dataset:**
We have trained the model on [ModelNet10](https://modelnet.cs.princeton.edu/) models. The obtained accuracy on this dataset is close to the original score of 89%. 

### **Required Packages:**

- Trimesh
- Numpy, Pandas
- Keras, Tensorflow

### **Steps to Run:**

The weights of the trained model is saved in the PointNet10 Folder.
To run the pre-trained model for catagorising 3D assests:
- Add the .obj/.ply files in the Models Directory.
- Run the ```Catagorise3D.py``` python script.

Alternatively this can be achieved through running the ```Catagorise3D.ibpny``` notebook in Google Colab. 


### **Result:**
We obtain
- ```3DAsset.csv``` containing the Models beside their predicted class.
- ```2DAsset.csv``` with the information of images with their classes.
