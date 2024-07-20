# aws-s3-versioning-replication Project


In this mini-project, I will delve into the versioning and replication features of Amazon S3. The steps include creating an S3 bucket, enabling versioning, configuring cross-region replication, and testing both the versioning and replication functionalities.

### The tools used for this project are:

    1. GitHub: To save my documentation online and for version control.

    2. Git: To clone my repository, create folders, and push my documentation.

    3. Snipaste: For capturing snapshots of images for my documentation.

    4. Visual Studio Code: For writing the documentation.

    5. Markdown: For formatting the documentation.

The following provides a step-by-step approach to how I was able to achieve the project goal:

### Task 1: Create an S3 Bucket
    1. Log in to AWS Management Console.
    2. Navigate to S3 Service.
    3. Create a new bucket:
    4. Click on “Create bucket”.
    5. Enter a unique bucket name.
    6. Choose a region
![](./img/Task1-Create-an-S3-Bucket/1.bucket-name-and-region.png)

7. Configure bucket settings as needed (e.g., block public access).
![](./img/Task1-Create-an-S3-Bucket/2.block-public-access.png)

8. Click “Create bucket”.
![](./img/Task1-Create-an-S3-Bucket/3.click-create-bucket.png)
![](./img/Task1-Create-an-S3-Bucket/4.bucket-created.png)

### Task 2: Enable Versioning
- Open the S3 bucket you created.
- Navigate to the “Properties” tab.
![](./img/Task2-Enable-Versioning/1.s3-properties.png)

- Scroll to the “Versioning” section.
- Click “Edit”
![](./img/Task2-Enable-Versioning/2.Scroll-to-the-Versioning-edit.png)

- Enable versioning.
- Save changes.
![](./img/Task2-Enable-Versioning/3.enable-versioning-save.png)

### Task 3: Configure Cross-Region Replication
- In the S3 bucket properties, navigate to the “Management” tab.
- Click on “Replication” and “Create replication rule”.
![](./img/Task3-Configure-Cross-Region-Replication/1.s3-management-replication-rule.png)

Provide the replication rule ID
![](./img/Task3-Configure-Cross-Region-Replication/2.replication-rule-ID.png)

### Configure the replication rule:
    To configure the replication rule, I will create another bucket in a different region and set up a new IAM role policy that grants access to all necessary S3 functions for replication.

### Steps to Create Another S3 Bucket in a Different Region
Create a New Bucket:
- Navigate to S3 Service.
- Click on “Create bucket”.
- Enter a unique bucket name
- Choose a different region from the source bucket
![](./img/Task3-Configure-Cross-Region-Replication/Create-Another-S3-Bucket-in-a-Different-Region/1.name-and-region.png)

- Block public access
![](./img/Task3-Configure-Cross-Region-Replication/Create-Another-S3-Bucket-in-a-Different-Region/2.block-public-access.png)

- Enable versioning
![](./img/Task3-Configure-Cross-Region-Replication/Create-Another-S3-Bucket-in-a-Different-Region/3.enable-versioning.png)

- Click “Create bucket”.
![](./img/Task3-Configure-Cross-Region-Replication/Create-Another-S3-Bucket-in-a-Different-Region/4.create-bucket.png)

### Steps to Create IAM Role for Replication
- Navigate to the IAM service.
- Click on “Roles” in the sidebar, then click “Create role”.
![](./img/Task3-Configure-Cross-Region-Replication/Create-IAM-Role-for-Replication/1.click-create-role.png)

- Select “AWS service” as the type of trusted entity.
- Choose “S3” as the service that will use this role.
- Click “Next”.
![](./img/Task3-Configure-Cross-Region-Replication/Create-IAM-Role-for-Replication/2.AWS-service-and-use-case-then-Next.png)

Attach Permissions Policies:

Attach the following policies:
- AmazonS3FullAccess
- Click “Next”.
![](./img/Task3-Configure-Cross-Region-Replication/Create-IAM-Role-for-Replication/3.full-access-policy-NEXT.png)

- Give the role a meaningful name
![](./img/Task3-Configure-Cross-Region-Replication/Create-IAM-Role-for-Replication/4.role-name.png)

- Review the permissions and click “Create role”.
![](./img/Task3-Configure-Cross-Region-Replication/Create-IAM-Role-for-Replication/5.create-role.png)

### Steps to Configure Replication Rule
- Source bucket: The bucket I created initially.
![](./img/Task3-Configure-Cross-Region-Replication/3.source-bucket.png)

- Destination bucket: The new bucket I created in a different region.
![](./img/Task3-Configure-Cross-Region-Replication/4.destination-bucket-and-region.png)

- IAM Role: Select the IAM role I created
![](./img/Task3-Configure-Cross-Region-Replication/5.choose-IAM-role.png)

- Review the replication rule settings.
- Save the rule.
![](./img/Task3-Configure-Cross-Region-Replication/6.save.png)

- Replication rule successfully created
![](./img/Task3-Configure-Cross-Region-Replication/7.replication-rule-created.png)

### Task 4: Test Versioning
- Upload an object to the S3 bucket.
![](./img/Task4-Test-Versioning/1.object-uploaded.png)

Modify the object:
- Upload a new version of the same object.
![](./img/Task4-Test-Versioning/2.object-uploaded-version.png)

Observe versioning behavior by checking the version history.
1. Go to the object.
2. Click on “Versions” to see all versions of the object.
![](./img/Task4-Test-Versioning/3.all-versions-of-my-OBJECT.png)

### Task 5: Test Replication
Verify replication:
- Check the destination bucket in the other region to ensure the object has been replicated.
![](./img/Task5-Test-Replication/2.replication-confirmed-1.png)

- Version history of the replicate.
![](./img/Task5-Test-Replication/1.replication-confirmed-2.png)

### Importance of S3 Versioning in Maintaining Object History
S3 versioning and cross-region replication are essential features that significantly contribute to data protection, integrity, and availability. By maintaining a comprehensive history of object versions and ensuring geographic redundancy, these features provide robust solutions for data resilience and disaster recovery, enhancing the overall reliability of cloud storage solutions.

### Conclusion
In this mini-project, I explored the versioning and replication features of Amazon S3. The project involved creating an S3 bucket, enabling versioning, configuring cross-region replication, and testing both versioning and replication functionalities.