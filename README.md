# Nardine-Here is a Blog on how i hosted a static website using cloud storage and a CDN. 

Firstly ,this the Architecture Diagram and narrations;
[User Browser] ---> [CDN (CloudFront / Azure CDN / Cloud CDN)] ---> [Cloud Storage Bucket]
                                               |
                                               ---> [Custom Domain + SSL (via DNS)]
•Cloud Storage- Hosts Static files (HTML,CSS,JS,Images)
•CDN- Delivers content globally with low latency 
•DNS + SSL- Provides a custom domain and HTTPS Security.

This is the list of Cloud services Used.For this project i used Amazon Web Services(AWS).
•Amazon S3- Stores static website Files
•Amazon cloudfront- Acts as the CDN for global caching qnd faster delivery.
•Amazon Route 53- Manages custom domain and DNS routing. 
•AWS certificate  Manager(ACM)- Provides SSL/TLS certificate for HTTPS. 

Here is a step-by -step Deployment Guide;
1.Created a storage bucket
•Go to S3 ->create a bucket(eg.Bernardinestaticwebsite)
•Enable public Access
•Upload website files(index.html,style.css,images etc)

2.Enable static website Hosting.
•In s3 ->properties ->Enable "Static website Hosting"
•Set index.html as the default root object

3.Setup CDN (Cloudfront)
•create a cloudfront distribution
•Set S3 buckets as the origin 
•Enable caching and choose "Redirect HTTP to HTTPs"

4.Connect Custom Domain
•In Amazon Route 53->create a hosted zone for your domain
•Update DNS records at your registrar to point to Route 53
•Add an Alias record pointing to the cliyd front distribution. 

5.Add SSL/TLS for HTTPs
•Request a certificate in AWS certificate Manager (ACM).
•Attach the certificate to your cloud front distribution

6. Test Deployment
•Visit your domain->your website should load securely. 

i hope this helps anyone trying to host a static website on AWS and to my fellow cloud architects and practitioners how did do with these steps stated. 😊😊