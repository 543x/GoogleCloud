
# Google Cloud Functions Pub

This recipe shows you how to publish messages to a Cloud Pub/Sub topic from a
Cloud Function.

View the

## Deploy and Test

1. Follow the [Cloud Functions quickstart guide][quickstart] to setup Cloud
Functions for your project.

1. Clone this repository:

        git clone https://github.com/GoogleCloudPlatform/nodejs-docs-samples.git
        cd nodejs-docs-samples/functions/pubsub

1. Create a Cloud Pub/Sub topic (if you already have one you want to use, you
can skip this step):

        gcloud beta pubsub topics create YOUR_TOPIC_NAME

    * Replace `YOUR_TOPIC_NAME` with the name of your Pub/Sub Topic.

1. Deploy the `publish` function with an HTTP trigger:

        cd publish/
        gcloud functions deploy publish --trigger-http --runtime YOUR_RUNTIME

    * Replace `YOUR_RUNTIME` with the name of the runtime you are using. For a
    complete list, see the [gcloud reference](https://cloud.google.com/sdk/gcloud/reference/functions/deploy#--runtime).

1. Deploy the `subscribe` function with the Pub/Sub topic as a trigger:

        cd subscribe/
        gcloud functions deploy subscribe --trigger-topic YOUR_TOPIC_NAME --runtime YOUR_RUNTIME

    * Replace `YOUR_TOPIC_NAME` with the name of your Pub/Sub Topic.

1. Call the `publish` function:



    * Replace `YOUR_TOPIC_NAME` with the name of your Pub/Sub Topic.

1. Check the logs for the `subscribe` function:

        gcloud functions logs read subscribe

    You should see something like this in your console:

        D      ... User function triggered, starting execution
        I      ... Hello World!
        D      ... Execution took 1 ms, user function completed successfully

[quickstart]: https://cloud.google.com/functions/quickstart
