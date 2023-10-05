# Pipeline Definition<a name="dp-how-pipeline-definition"></a>

 A pipeline definition is how you communicate your business logic to AWS Data Pipeline\. It contains the following information: 
+  Names, locations, and formats of your data sources 
+  Activities that transform the data 
+  The schedule for those activities 
+  Resources that run your activities and preconditions 
+  Preconditions that must be satisfied before the activities can be scheduled 
+  Ways to alert you with status updates as pipeline execution proceeds 

From your pipeline definition, AWS Data Pipeline determines the tasks, schedules them, and assigns them to task runners\. If a task is not completed successfully, AWS Data Pipeline retries the task according to your instructions and, if necessary, reassigns it to another task runner\. If the task fails repeatedly, you can configure the pipeline to notify you\. 

 For example, in your pipeline definition, you might specify that log files generated by your application are archived each month in 2013 to an Amazon S3 bucket\. AWS Data Pipeline would then create 12 tasks, each copying over a month's worth of data, regardless of whether the month contained 30, 31, 28, or 29 days\. 

You can create a pipeline definition in the following ways: 
+  Graphically, by using the AWS Data Pipeline console 
+  Textually, by writing a JSON file in the format used by the command line interface 
+  Programmatically, by calling the web service with either one of the AWS SDKs or the [AWS Data Pipeline API](https://docs.aws.amazon.com/datapipeline/latest/APIReference/Welcome.html) 

 A pipeline definition can contain the following types of components\.Pipeline Components

[Data Nodes](dp-concepts-datanodes.md)  
The location of input data for a task or the location where output data is to be stored\.

[Activities](dp-concepts-activities.md)  
A definition of work to perform on a schedule using a computational resource and typically input and output data nodes\.

[Preconditions](dp-concepts-preconditions.md)  
A conditional statement that must be true before an action can run\. 

[Scheduling Pipelines](dp-concepts-schedules.md)  
Defines the timing of a scheduled event, such as when an activity runs\.

[Resources](dp-concepts-resources.md)  
The computational resource that performs the work that a pipeline defines\.

[Actions](dp-concepts-actions.md)  
An action that is triggered when specified conditions are met, such as the failure of an activity\.

 For more information, see [Pipeline Definition File Syntax](dp-writing-pipeline-definition.md)\. 