# Node.js Google Cloud Storage

This sample demonstrates how to use [Google Cloud Storage](https://cloud.google.com/storage/)
on [Google App Engine flexible environment](https://cloud.google.com/appengine).

## Setup

Before you can run or deploy the sample, you will need to do the following:

1. Enable the Cloud Storage API in the [Google Developers Console](https://console.developers.google.com/project/_/apiui/apiview/storage/overview).

1. Create a Cloud Storage Bucket. You can do this with the [Google Cloud SDK](https://cloud.google.com/sdk)
with the following command:



1. Set the default ACL on your bucket to public read in order to serve files
directly from Cloud Storage. You can do this with the [Google Cloud SDK](https://cloud.google.com/sdk)
with the following command:

        

1. Update the environment variables in `app.yaml`.

## Running locally

Refer to the [top-level README] for instructions on running and
deploying.

When running locally, you can use the [Google Cloud SDK](https://cloud.google.com/sdk)
to provide authentication to use Google Cloud APIs:

    gcloud init

Then set environment variables before starting your application:


