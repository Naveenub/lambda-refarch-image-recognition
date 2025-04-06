# 🧠 Serverless Image Recognition Pipeline on AWS

This project implements a fully **serverless image recognition system** using [AWS Lambda](https://aws.amazon.com/lambda/), [Amazon Rekognition](https://aws.amazon.com/rekognition/), [Amazon S3](https://aws.amazon.com/s3/), and related AWS services.

Whenever an image is uploaded to an S3 bucket, the system automatically analyzes the image for objects, scenes, faces, and stores the recognition results in DynamoDB. You can then access this data using an API exposed via Amazon API Gateway.

---

## 🏗️ Architecture

This reference architecture includes:

- **Amazon S3** – Triggers the pipeline when a new image is uploaded.
- **AWS Lambda** – Processes the image and integrates with Rekognition.
- **Amazon Rekognition** – Detects objects, faces, and scenes in the image.
- **Amazon DynamoDB** – Stores the extracted metadata.
- **Amazon SNS** *(optional)* – Sends notifications or events.
- **Amazon API Gateway** – Provides access to recognition results.

### 📸 Flow Diagram

User → S3 (image upload)
     ↓
Lambda (triggered by S3)
     ↓
Rekognition (analyze image)
     ↓
DynamoDB (store metadata)
     ↓
SNS (notify)
     ↓
API Gateway (query results)

🔧 Getting Started
Prerequisites
-> AWS CLI configured (aws configure)

-> AWS SAM CLI installed (install guide)

-> Node.js and npm installed

🚀 Deployment
1. Clone this repo
git clone https://github.com/aws-samples/lambda-refarch-imagerecognition.git
cd lambda-refarch-imagerecognition

2. Install dependencies (if applicable)
npm install

3. Build and deploy the application using AWS SAM
sam build
sam deploy --guided

✅ Usage
1. Upload an image to your deployed S3 bucket
aws s3 cp ./images/cat.jpg s3://<your-s3-bucket-name>/

2. The Lambda function is triggered automatically
-> It calls Amazon Rekognition
-> It stores labels and metadata in DynamoDB

3. Query metadata via the API
You can access the API Gateway endpoint returned by the deployment and make a GET request using tools like curl, Postman, or a browser.

🔍 Example Use Cases
✅ Real-time content moderation
🧠 AI-powered photo categorization
🕵️ Facial recognition & scene detection
🗂️ Image metadata enrichment for media
🎥 Event-driven processing of surveillance footage

🧱 Technologies Used
-> Amazon S3
-> AWS Lambda
-> Amazon Rekognition
-> Amazon DynamoDB
-> Amazon API Gateway
-> Amazon SNS (Optional)
-> AWS SAM CLI

🧪 Testing
You can upload test images from the images/ directory provided or use your own. Make sure the images are under 5MB for optimal Lambda and Rekognition performance.

🧾 License
This project is licensed under the Apache 2.0 License. See the LICENSE file for details.

🙌 Acknowledgements
This is an official AWS Samples project showcasing serverless and AI capabilities. For more AWS solutions and architecture examples, visit AWS Samples.

🤝 Contributing
Have improvements or ideas? Contributions are welcome!
# Fork the repository
# Create a new feature branch
# Submit a pull request
