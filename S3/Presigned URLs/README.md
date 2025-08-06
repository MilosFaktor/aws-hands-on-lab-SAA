# 🔐 S3 Pre-Signed URL – Secure Temporary Access to Private Objects

This hands-on lab demonstrates how to securely access a private S3 object **without exposing the bucket to public access**, using an **AWS pre-signed URL**.

---

## Key Concepts

- S3 **pre-signed URLs** allow time-limited access to **private objects**.
- The bucket **remains private**, but specific files can be accessed securely.
- Ideal for sharing resources **temporarily** without altering bucket policies.

---

## Steps Performed

1. ✅ **Create a private S3 bucket**:
   - Bucket name: `presigned-test-2df23rfre4`
   - Block all public access (default setting)

2. ✅ **Upload an object to the bucket**:
   - File: [Presigned URL Example](presigned_index.html)
   - Method: AWS Console or CLI

3. ✅ **Generate a pre-signed URL** using AWS CLI:
   ```bash
   aws s3 presign s3://presigned-test-2df23rfre4/presigned_index.html
    ```
4. ✅ **Access the file** using the generated URL:
   - Open the URL in any browser
   - Observe the secure, temporary access without public permissions

## Screenshots

- [Presigned URL generation](Screenshots/presigned_url_generation.png)
- [Website access via presigned URL](Screenshots/Website_access_via_presigned_url.png)


## Key Learning
 Pre-signed URLs allow controlled access to private S3 objects,
perfect for temporary file sharing or secure object access in apps.

#AWS #S3 #PresignedURL #AWSCloudShell #AWSSecurity #Serverless #AWSHandsOn #CloudProjects #SolutionArchitect