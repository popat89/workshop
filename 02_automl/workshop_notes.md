
01

boto3 and sagemaker: python sdks to interact with python resources

df.query('star_rating == 5') vs. df[df.star_rating == 5] ??

choosing to downsample down to the minority class - OK if the majority class is not highly variable

when doing test_train_split, do train and holdout, then split the hold out into validation, test

What is explode? 
explode = (0.1, 0, 0)  
fig1, ax1 = plt.subplots()
ax1.pie(sizes, explode=explode, labels=labels, autopct='%1.1f%%', startangle=90)

Store info from this notebook - even after you shutdown the notebook kernel, if you use store, you can use the variables - neat. 
%store header_train_s3_uri

Clean up the kernel: 
%%javascript
Jupyter.notebook.save_checkpoint();
Jupyter.notebook.session.delete();


02_Train_Reviews_AutoPilot
recall stored variables: %store -r header_train_s3_uri

this is created on the sagemaker slient we started at the beginng of the notebook
sm.create_auto_ml_job(AutoMLJobName=auto_ml_job_name,
                      InputDataConfig=input_data_config,
                      OutputDataConfig=output_data_config,
                      AutoMLJobConfig=job_config,
                      RoleArn=role)
This is a programatic creation in the notebook so that I do not have to go out to the UI to keep doing things

AutoML will generate notebooks!! What?? 
It comes back with automated suggestions of what we can use and then gives you a starting baseline to continue 
exploration. This is a pretty cool automation and a great way to quickly learn and explore. 

in the generated_module folder we are given the python snippets

comprehend is another automated ml type option that can do classification - I don't think comprehend will provide the notebooks and such though?
comhrehend is built in to perform nlp tasks, takes some model and then finetunes the prebuiilt model to our own data, Antje not sure what that model uses.

Human in the looop - augmented AI to help our labeling team out. Not covered in the workshop, but can review thee code later.  









