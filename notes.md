# my own notees

install mlflow using below command.. 


go tto deployment/mlfow and run docker compose -f docker-compose.yaml  up -d 


Data Engineer : RAW Data --> 

    How to collect data sources : kaggle.com (for sample dataset for testing )
    df.shape help to get the size of data

Data Scinest
    EDA : Experimental data amalysit
    feature Eningenring : add extra  feature coulmn based on exisitng coulmn, engineer new feature of data , feature spliting , ecoding to set new feature (tshirt size example) binary encoding vector encoding
    expirementation Data: for expirement data we need to convert our data into x and y trail. X (input) is used to make decision and what the model has to predict is y (output). train is 80% of data we use and Test 20 % data to use (test and train actualy dataset spliting )

    Algorithem : use to create model, each algorithem has diffirent hyper parameters to finetune the model
        LinearRegresion
        RandomForest
        gradinaboosting
        XGBRegressor 
    Pickle file : should be model.pkl file 

    Data Scinece to Devops ML engineer to handover
        Model config
        Notebooks ( Machine lerrning engineer convert the notebook into code , should be feature.py, model_training.py)
        Model ( decide by the data scince and created thorugh the code that ML engineer create it. should be in the form of model.pkl)
        Preprocessor.pkl (Required when we want an input from web ui)

        RSET API : take preprocessor.pkl and model.pkl and wrap it up in hte REST API(FAST API) so user can intract to it.

        WeB UI ( Web Client) : we can use streamlit lib to build the ui

    Steamlit lib to create ui and FastAPI for RestAPI

    ML workflow pipeline using github action : -
        ML workflow : 
            Data - > ingest/process data - > Future Enginering - > model training - > package -> (CD) deployment
        Modular Pipeline - > 
            Data Ingestion and processing pipeline : 
            Feature Enginering Pipeline :
            Model Training pipeline: 
                1. register model ( eg. MLFlow Registery , SageMaker)
            Model Packaging  & CI Pipeline
            Deployment Pipeline

        DAG Tool : mostely the argo tool, which is directed going to one direction ( e.g Argo Workflow, kubeflow, apache workflow, metaflow)


   
DevOps Engineer


Workflow sample


name : test pipeline
on: 
    push:
     brnach:[main]
    pull_request:
      branch:[main]

jobs:
  build:
    run_on : ubuntu-latest
    steps:
    - name : checkout code
      uses: action/checkout@v3
