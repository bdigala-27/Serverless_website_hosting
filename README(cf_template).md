
- **Parameters**:
  - This section allows you to provide custom values for certain settings when creating the stack.
  - You can specify the name of the bucket, the name of your organization, and the name of your workspace.

- **Resources**:
  - This section defines the actual AWS resources that will be created.
  - **WebsiteBucket**:
    - Creates an S3 bucket with the name you provided.
    - Configures the bucket to allow public access to its contents.
    - Sets the ownership controls for objects in the bucket.
  - **WebsiteBucketPolicy**:
    - Applies a policy to the bucket that allows anyone to read (access) the files stored in the bucket.
  - **WebsiteContentIndex**, **WebsiteContentStyle**, **WebsiteContentError**:
    - Uploads the HTML, CSS, and error page files for your website to the S3 bucket.
  - **WebsiteBucketWebsiteConfiguration**:
    - Configures the S3 bucket to serve as a static website.
    - Specifies the "index.html" file as the default file to be displayed when someone visits your website.
    - Specifies the "error.html" file to be displayed in case of any errors.
  - **WebsiteCloudFrontDistribution**:
    - Creates a CloudFront distribution, which is a global content delivery network (CDN) service.
    - Configures the S3 bucket as the origin (source) for the content to be served through CloudFront.
    - Sets up caching rules to improve performance by serving content from CloudFront's edge locations.
    - Enables HTTPS for secure access to your website.

- **Outputs**:
  - This section defines the URLs that will be displayed after the stack is created successfully.
  - **WebsiteURL**: The URL for accessing your website hosted on the S3 bucket.
  - **WebsiteCloudFrontURL**: The URL for accessing your website through the CloudFront distribution (CDN).