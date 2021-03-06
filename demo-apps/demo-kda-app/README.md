## Kinesis Data Analytics Demo Consumer

This is a simple Flink application to consume data from a Kinesis stream.

Here's the schema for the payload:

```
{
    "name": "EmployeeInfo",
    "namespace": "com.amazonaws.services.kinesisanalytics.payloads",
    "type": "record",
    "fields": [
        {
            "name": "companyid",
            "type": "long"
        },
        {
            "name": "employeeid",
            "type": "long"
        },
        {
            "name": "mname",
            "type": "string"
        },
        {
            "name": "dob",
            "type": "string"
        },
        {
            "name": "eventtimestamp",
            "type": "long"
        }
    ]
}
```

## Running the app locally

```
mvn clean compile exec:java \
         -Dexec.mainClass="com.amazonaws.services.kinesisanalytics.DemoKDAApp" \
         -DAWS_REGION="[YOUR REGION]" \
         -DKINESIS_STREAM="[YOUR KINESIS STREAM]" \
         -DSHARD_USE_ADAPTIVE_READS="true"
```

## Deploying to Kinesis Data Analytics for Apache Flink

Please refer to the [Getting Started](https://docs.aws.amazon.com/kinesisanalytics/latest/java/getting-started.html) developer guide for information on setting up your AWS account, the AWS CLI, and on deploying an Apache Flink app to Kinesis Data Analytics.