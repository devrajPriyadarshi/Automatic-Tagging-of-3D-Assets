
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

The weights of the trained model is saved in the ```PointNet_model.tf``` Folder. The training script is available in the ```train.ipynb``` notebook, which also outputs the saved model with weights so that they can be further updated and used. 

To run the pre-trained model for catagorising 3D assests:
- Add the .obj/.ply files in the ```Models``` Directory.
- Run the ```Catagorise3D.py``` python script.

Alternatively this can be achieved through running the ```Catagorise3D.ipynb``` notebook in Google Colab, just make sure to add the models in the proper directory. [**Preferred and Tested**]. 


### **Result:**
We obtain
- ```3DAsset.csv``` containing the Models beside their predicted class.
- ```2DAsset.csv``` with the information of images with their classes.
- The ```Catagorised``` folder filled with models and images sorted according to their classes.

### Limitations:
- Since ```.fbx``` is a proprietary file format owned by Autodesk, there aren't any opensource format change program written in python. The only available option is to covert it online through some website or software like Blender.
- Assets download from the internet can have any rotation in 3D. Therefore a Rotation Invariant implementation of PointCloud Model is neccessary to overcome this: [RiConv](https://github.com/hkust-vgd/riconv)
- Further explanding on the number of classes will require different datasets. Some prospects would be [ModelNet40](https://modelnet.cs.princeton.edu/) or [ShapeNet](https://shapenet.org/)