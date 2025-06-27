# Host a Website on Amazon S3

Host a Website on Amazon S3

You can use Amazon S3 to store and retrieve any amount of data at any time from anywhere on the web. This is what we'll be creating today!

Project architecture diagram

In this project, you'll use Amazon S3 (which stands for Amazon Simple Storage Service) to host a website.

Websites are run by pictures and files. You'll be hosting (which basically means make public on the Internet) a website on Amazon S3 by uploading website content into S3 and then making it publicly accessible


## Step 1:
Login to aws console

And choose Mumbai region. This is region is very closest to me that’s why I choose Mumbai.

Create a bucket in Amazon S3

In the AWS Management Console, search for S3.

Choose create bucket

AWS region select the region closest to you

For bucket name, give any name (static-website-project-rushikesh)

An S3 bucket name is globally unique, and all AWS accounts share the namespace. After you create a bucket, no other AWS account in the entire world can use your bucket's name unless you delete the bucket.

For object ownership, choose ACLs enabled.

what are ACLs (Access Control Lists)?
An ACL = a set of rules that decides who can get access to a resource.

Enabling ACLs in this S3 setup lets you control who can access and do things with the objects (i.e. website files) you upload into your bucket.

With ACLs, different AWS accounts can own and control different files in your bucket.

The warning that pops up suggests that it's simpler to use something called "bucket policies". While they let you control access for the entire bucket (e.g. making the entire bucket and its objects public), bucket policies don't give you fine grained control over individual objects in your bucket.

Bottom line, if you know that the entire bucket contains no sensitive information, you can use a bucket policy. But if there's even one object in the bucket that you want to keep private, use ACLs.

In this exercise, we're enabling ACLs to show you how they work.

Choose bucket owner preferred.

For block public access setting for this bucket, clear the check box for block all public access.

A yellow banner has popped up! This banner is telling us that the bucket and its objects might become public if we untick the checkbox. This is what we want to host a public website!

Check the box that say.

I acknowledge……

For bucket versioning, choose enable.

Once you turn on (enable) bucket versioning, you can't turn it off. We'll show you why we've enabled this as a last step in this exercise.

Choose create bucket.


## Step 2:
Upload website content to your bucket

Time to get your website's files in your bucket!

In the Buckets section, choose the name of your new bucket.

Upload these files into your bucket (right click on each link, and select Save link as...):

Styles.css

What is HTML?
HTML (HyperText Markup Language) is used to create and design web pages. It's your way of telling the website where you want to display your text, images, videos and more. Think of HTML as the blueprint that shapes what you see when you visit a website.

Unzip the zip file you've downloaded.

Return to the Amazon S3 console with your bucket page open. Choose the Objects tab.

Choose Upload.

Choose Add files.

Choose index.html. and Styles.css

You might get a popup that tells you that all files in that folder will be uploaded.

Choose Upload.

S3 will get to work right away!

Your files should upload in a few minutes! Choose Close when you see the green Upload succeeded banner.


## Step 3:
Configure a static website on Amazon S3

Now let's set up the bucket for static website hosting!

What does website hosting mean?
Website hosting is what makes your website public on the internet.

Even if you perfect an HTML file, no one else can see it when it's stored as a local file on your computer! Website hosting = storing your HTML file (and the other files for your website) on a web server, so it's accessible online.

By configuring your S3 bucket for hosting, we're telling this bucket: "please create a URL that will take anyone to a page that displays the HTML file I just uploaded."

  Make sure you're back in your bucket's page. If you're not sure, choose buckets on the left hand side navigation bar, and then choose the bucket you created for this project.

  Choose the Properties tab.

  Scroll allllllllll the way down to the Static website hosting panel.

  Choose Edit.

  Configure the following settings:

Static web hosting: Choose Enable.

Hosting type: Choose Host a static website.

Index document: Enter index.html

  choose Save changes.

  In the Static website hosting panel under bucket website endpoint, click on the URL.

  An error! 👀

Why did I get this error?
Objects (in this case, the HTML and images files you uploaded) are private by default. This default setting helps keep your account's data secure.

The error message you're seeing is telling you that your static website is being hosted by S3, but the actual HTML/image files you've uploaded are still private. It's kind of like having a bucket on display, so everyone can see the bucket - but the contents are covered up, preventing anyone from seeing what's inside.

To solve this error, we need to set the permission of the objects to public - this is why we enabled ACLs in Task 1!


## Step 4:
Use ACLs to make objects in your S3 bucket public

Let's make the uploaded objects publicly accessible so users can view your website.

Keep the error message tab open and switch back to the Amazon S3 console tab.

Would you still remember how to view your S3 bucket's objects? Try finding your bucket's Objects page and making your objects public using ACLs.

.... feeling a little stuck?

No worries! If you're stuck, head to the Objects tab.

Select the checkboxes next to your index.html file and the folder of website assets.

In the Actions dropdown, choose Make public using ACL.

Choose Make public.

Once the green banner pops up, choose Close.

  Return to the web browser tab that has the 403 Forbidden message.

  Refresh the tab.

Delete your resources

Delete your resources

Make sure you delete all your resources to avoid getting charged. This is a super important task for every single project you set up.

We challenge you to try to give this a go yourself 💪 Do you think you can delete the resources you've created today? Don't forget to take screenshots of your work before they're gone!

If you're feeling stuck (we've all been there!), here's a little guide:

To delete an S3 object, head back to your browser tab with the AWS Management Console.

Select the Objects tab.

Select the checkboxes next to the three objects in your bucket, and choose Delete.

Type delete to confirm.

Select Delete objects.

