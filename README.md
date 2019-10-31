# FileIntegrationDemo

This project features an integration use case through WSO2 Integration Studio 6.5. It demonstrates reading a CSV file from a local file repository, parsing the data to Json and persist the data to MongoDB which is exposed through a data service in WSO2 Enterprise Integrator.

Before you run the sample, please make sure you have completed the following steps,

- Give the correct file paths for "transport.vfs.FileURI", "transport.vfs.MoveAfterFailure"  and  "transport.vfs.MoveAfterProcess" parameters which you can find in FileProxy.xml (These are the locations from where the file will be read, moved at the event of failure and moved after successful processing)
- The file used for the integration is “patientRecords.csv” which you can find inside the “~/FIle/In” path of this repository. Make sure to copy the file to the folder path defined in "transport.vfs.FileURI" in the above step.
- Follow the link [1] to create a data service to expose MongoDB data. Here I have created a POST resource as following which is mapped to the end point definition in mongoEndpoint.xml. Also create GET resources with the desired criteria to execute certain queries on the saved data.

| Resource Path | Resource Method |
| --- | --- |
| addPatientRecord | POST |

Once you are done with the above steps create the CAR (Carbon Application Archive) file [2] and run the sample [3]
	
[1] https://docs.wso2.com/display/EI650/Exposing+MongoDB+as+a+Data+Service
[2] https://docs.wso2.com/display/EI650/Working+with+WSO2+Integration+Studio#WorkingwithWSO2IntegrationStudioPackagingESBartifact
[3 ]https://docs.wso2.com/display/EI650/Working+with+WSO2+Integration+Studio#WorkingwithWSO2IntegrationStudio-TestingtheESBartifacts
