# AdaptiveAlgo Test

## Q1:
For the question 1, we had to create a docker container with a Data Science environment, using the Rapidsai build tool. 

Preliminary steps: 
Prerequisites for using Rapidsai tool should be installed and updated on the Pc you are using (in my case GCP instance with GPU).   
1.https://rapids.ai/start.html  
2.Install docker-ce  
3.Install nvidia-docker  
4.Install required nvidia drivers  
5.Docker login

First Step:    
Clone the rapidsai/build repository in the GCP/EC2 instance
```
https://github.com/rapidsai/build.git
```

Second Step:  
Build an image with an particular template 
```
sudo bash rapidsdevtool.sh buildDockerImage  -t ubuntu-devel –i adi6496/adityak-adaptivealgo-new
```

Third Step:
```
sudo docker run --runtime=nvidia \
        --rm -it \
        -p 8888:8888 \
        -p 8787:8787 \
        -p 8786:8786 \
        adi6496/adityak-adaptivealgo-new
```

To run the Jupyterlab use      
```
bash utils/start-jupyter.sh
```

Fourth Step:  
Pull the image from Docker hub
```
sudo docker pull adi6496/adityak-adaptivealgo-new
```
**NOTE: This will run JupyterLab on port 8888 on your host machine.**



## Q2  
The Repo2Docker tool creates a Docker image from a repository. The tool requires a 'requirement.txt' file in the repository.
The requirements.txt file needs to have all the libraries necessary to run the files in your repository.  
Example: Lets say I have a repository with .py files containing different libraries like pandas, numpy, keras etc, 
I will have to add a "requirements.txt" file with the 

## Q3
Third question was to use the tool built for a data science project
The Machine learning project which I was working on is a Kaggle competition on Sentiment Analysis Review of a Rotten Tomato dataset. 
Preprocessing:
Stemming
Word tokenize
Data Sampling (as data is biased towards neutral)

Model training
Embedding layer
LSTM layer
Dense layer

Training accuracy ~ 80% 
Validation accuracy ~ 75%



