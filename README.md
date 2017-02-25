# AWS-Rekognition

The start of a browser application using the [AWS SDK for JavaScript in the Browser](https://aws.amazon.com/sdk-for-browser/), [Rekognition](https://aws.amazon.com/rekognition/), and [S3](http://aws.amazon.com/s3).

## Get started

    git https://github.com/joshhoneycutt/AWS-Rekognition.git
    cd AWS-Rekognition

## AWS Account

You need an [Amazon Web Services](https://aws.amazon.com/console/) account to use the the AWS SDK, Rekognition, and S3. You'll likely stay in the free tier, but will need a credit card.

## Secret Keys

See the [Security Credentials](http://aws.amazon.com/security-credentials) page to get access and secret keys.

## Create a secrets.js file

    touch secrets.js

This creates a secrets.js file. Enter your access key, secret access key, and region. Separate keys out and keep them safe .gitignore. It will look like this:

	const myAccessKeyId = 'YOUR_ACCESS_KEY';
	const mySecretAccessKey = 'YOUR_SECRET_ACCESS_KEY';
	const myRegion = 'YOUR_REGION';

The region here should be the same as your S3 bucket.

## Upload pictures to S3

Create an S3 bucket. Upload a couple pictures of yourself. Check out the [S3](http://aws.amazon.com/s3) documentation for how to do that. Make sure your S3 bucket is in the region you define in your secrets.js

## Update S3 bucket and picture variables

Update the variables at the top of rek.js with your own S3 bucket and 

	const yourS3Bucket           = 'jj-rek2';
	const yourSourceImageName    = 'joe1.jpg';
	const yourTargetImageName    = 'joe2.jpg';
	
	var params = {
	  SimilarityThreshold: 90,
	  SourceImage: {
	   S3Object: {
	    Bucket: yourS3Bucket,
	    Name: yourSourceImageName
	   }
	  },
	  TargetImage: {
	   S3Object: {
	     Bucket: yourS3Bucket,
	     Name: yourTargetImageName
	   }
	  }
	 };


## Run the code 

	open index.html

Currently, this website uses [Amazon Rekognition](https://aws.amazon.com/rekognition/) to look at 2 pictures in [Amazon Simple Storage Service (S3)](http://aws.amazon.com/s3), then compares if they are similar.
