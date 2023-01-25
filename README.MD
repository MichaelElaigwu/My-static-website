CREATING A STATIC WEBSITE WITH S3 

STEP 1
1. Download and unzip the repository of the content/objects
2. login to your aws management console
3. select s3 
4. upload the object locally to your s3 Bucket by dragging the content to the upload button on your s3 bucket
5. Objects uploaded successfully on your S3 bucket.
6. After uploading your objects to your s3 bucket, you have to make the bucket publicly readable to be access.

STEP 2
#Setting permissions for website access, When you configure a bucket as a static website, if you want your website to be public, you can grant public read access. To make your bucket publicly readable, you must disable block public access settings for the bucket and write a bucket policy that grants public read access:
1. Choose the name of the bucket that you have configured as a static website.
2. Choose Permissions.
3. Under Block public access (bucket settings), choose Edit.
4. Unclick Block all public access, and choose Save changes.

STEP 3
#To make the objects in your bucket publicly readable also, you must write a bucket policy that grants everyone permission, After you edit S3 Block Public Access settings, you can add a bucket policy to grant public read access to your bucket. When you grant public read access, anyone on the internet can access your bucket:
1. Under Buckets, choose the name of your bucket.
2. Choose Permissions.
3. Under Bucket Policy, choose Edit.
4. To grant public read access for your website, create a JSON script on the bucket policy, and paste it in the Bucket policy editor.
"The JSON script"
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::<Bucket-Name>/*"
            ]
        }
    ]
}

5. After that then save change.

STEP 4
#After creating the s3 bucket and making it publicly access and readable, you have to copy the url and paste it on your browser to view the static website you created with s3:
1. go back to your s3 bucket.
2. click on your bucket name you created with the objects you uploaded
3. click only on "index.html" on the object
4. Above copy the url.
5. Paste the url on your browser to view your static website.
