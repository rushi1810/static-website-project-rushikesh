# Host a Website on Amazon S3

You can use Amazon S3 to store and retrieve any amount of data at any time from anywhere on the web. This guide walks through how to host a static website using Amazon S3.

![Architecture Diagram](5901f9a7-7f09-4821-aa4c-690d5992e015.png)

---

## Step 1: Login to AWS Console

Select your closest region (e.g., Mumbai).

![AWS Console](6367e00a-e3e8-43c1-aa14-c9912b1d974d.png)

---

## Step 2: Create an S3 Bucket

Search for **S3** in the AWS Management Console and create a bucket.

![Create Bucket](0d9d37df-d676-46b8-a4a4-e2c1855474a7.png)

### Bucket Settings:

- Name: `static-website-project-rushikesh`
- Enable **ACLs**
- Choose **Bucket owner preferred**

![ACLs Settings](df446f5b-705f-4c8e-b561-0d71df10bc22.png)

### Disable Block Public Access

Uncheck **Block all public access**.

![Public Access Settings](11e1330e-d75a-411c-b037-2c0502459090.png)

---

## Step 3: Upload Website Files

Go to your bucket and upload `index.html` and `styles.css`.

![Uploaded Files](3c1feb36-2a3d-4245-b9eb-76491153af89.png)

---

## Step 4: Enable Static Website Hosting

Go to **Properties** and enable static website hosting. Set the index document to `index.html`.

![Static Website Hosting](60d1a59c-0332-48a7-93aa-52af621db513.png)

---

## Step 5: Make Objects Public

Use **Actions → Make public using ACL** to make the files accessible.

![Make Public ACL](6769fecb-6678-4c91-87b4-ef5909acdcfc.png)

---

## Final Result

Your static site is now live!

![Live Website](0be3eb4d-0b33-4b3c-8cab-8577838227aa.png)

---

## Cleanup

Delete your S3 bucket and its contents when you're done to avoid incurring charges.

---

📸 Remember to take screenshots of your steps if required.
