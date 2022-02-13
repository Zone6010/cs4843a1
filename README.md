## CS4843 - Assignment 1 by Zachary Bowman (raq506)

# Overview:
This is a project for Cloud Computing at UTSA by Zachary Bowman, made with
the intent of deploying a website using Amazon's S3 buckets and cloudfront
technologies found at: https://aws.amazon.com/.

Before beginning, create an HTML file that will be used as your "homepage",
aka the page your website will default to.  This will be important to getting
a workable website.

# Creation of an S3 Bucket
Before creating an S3 bucket, you should have an idea in mind of how you
want the website to run:  For a small group publically, or privately.  
Another thing to bear in mind is that you should create a file, for the
sake of a "homepage" for your website in HTML.

To begin the creation process, you goto https://s3.console.aws.amazon.com/s3/
then select "Create Bucket".  In the following screen the things to edit 
(to replicate my results) should be the text box areas labelled, "Bucket
Name" and "AWS Region".  Name your bucket something meaningful such as
"exampletests3" (this name will be used later in hooking up your cloudfront).

# Adding Objects, and Hosting Statically.

After your bucket is created, you should click on the name, which is now a link
inside the bucket list.  It will default to sending you to the Objects menu.  
Drag-and-Drop your HTML and objects into this area (or press upload, same results).

One all objects are inserted, goto the "Properties" tab and scroll to the bottom,
there will be asection titled, "Static Website Hosting", press "Edit" next to the title.
"Enable" static hosting, and set your "index file" to whichever HTML you want as
your "homepage".  Once done, press "save changes" at the bottom.

You now have a static website URL, which can be modifed to allow access to users, or
be used via CloudFront for better safety and faster delivery.

# Hosting Via Cloudfront

Once your S3 bucket is finished being set-up, we can begin working on our remote server
aka Cloudfront.  This is used for safer and faster remote access to your data in the bucket
for both clients and users alike.

To set up a Cloudfront, goto https://console.aws.amazon.com/cloudfront/v3/ . There you should
press the "Create Distribution" button.  Inside this new menu, you will want to look for the
"Origin Domain" text menu and input the name of your S3 bucket there with ".s3.amazonaws.com
added at the end.  (If using the name provided earlier it will be called "exampletests3.s3.amazonaws.com").
Scroll to the bottom and add a disription that is meaningful to the project at hand, such as:
"Cloudfront for exampletests3".  Once done, click "Create Distribution" at the bottom.

You will now have a link to a new Cloudfront, it will be named a jumble of letters and numbers,
which is why we add the description.  find the description you created before and click on the link
of letters and numbers to the left.  You will be sent to the "General" tab of this Cloudfront,
take note of the "Distribution Domain Name", this is how you will access your website.  On the 
"Settings" tab below, you will see an "edit" button, click this.  there will be a space for an,
"Default Root Object", put the title of your "homepage" in there.

Save, and wait for your website to deploy.  Once you have no more errors, or checks to wait on, 
use the link in the general tab titled "Distribution domain Name" and your HTML website should
be deployed in there. And with that, you have your baseline finished.
