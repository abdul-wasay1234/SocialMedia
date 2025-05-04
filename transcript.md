# Video Transcript for InstaShare Demo

## [0:00 - 0:20] Introduction
Hello everyone. My name is [Your Name] and today I will show you InstaShare, a scalable photo sharing platform I built using cloud technologies. This platform works like Instagram where creators can upload photos and consumers can view and interact with them.

## [0:20 - 0:40] Application Overview
Let me start by showing you the main parts of InstaShare. We have two types of users - creators who can upload photos, and consumers who can view and comment on photos. The application uses modern web design with Bootstrap styling that looks similar to Instagram. I've already set up two browser windows to demonstrate both user types simultaneously.

## [0:40 - 1:10] Azure Portal Overview
Now let's look at our Azure infrastructure. Here in the Azure Portal, you can see the resource group I created for this project. It contains all the cloud resources needed for our application. I've implemented multiple services to ensure scalability, including App Service, MySQL Database, Blob Storage, and Content Delivery Network.

## [1:10 - 1:40] Azure Database Configuration
Let's examine the Azure MySQL database configuration first. Here I've created a flexible server with appropriate compute and storage settings. In the networking tab, you can see I've configured private access with a virtual network for improved security. I've also set up firewall rules to allow connections only from our App Service and my development environment. The database contains tables for users, photos, comments, likes, and other necessary data structures.

## [1:40 - 2:10] Azure Blob Storage Setup
For media storage, I'm using Azure Blob Storage. Here you can see the container configuration where all photos are stored. I've set up lifecycle management policies to automatically move older, less accessed photos to cool storage tiers, saving costs. The storage account is connected to Azure CDN to cache images globally for faster access. You can see here the CORS settings I configured to allow our web application to securely access the stored images.

## [2:10 - 2:40] App Service Deployment Configuration
For hosting the application, I'm using Azure App Service. Here in the portal, you can see I selected the Premium tier to enable auto-scaling. In the deployment center section, I've configured external Git repository deployment rather than using FTP. This is much more efficient because with Git, I can push all changes at once and only the modified files are deployed. Let me show you the configuration settings where I enabled SCM deployment and authentication. This creates a webhook that automatically triggers deployments whenever I push code to the repository.

## [2:40 - 3:10] Networking and Security Configuration
In the networking section of the App Service, I've configured integration with a virtual network to ensure secure communication between the app and database. Here you can see I've set up custom domain and SSL settings with managed certificates for HTTPS. In the authentication section, I've implemented Azure Active Directory B2C for secure user authentication, which handles user identity management and scales better than custom solutions.

## [3:10 - 3:35] Continuous Deployment
Let me demonstrate how our deployment process works. When I make changes to the code, I use Git to commit and push those changes. Here's the terminal showing the Git commands. Once pushed, Azure automatically picks up the changes and deploys them. In the deployment logs, we can see the build and deployment steps, including installing dependencies from requirements.txt. This automated process ensures consistent deployments without manual file transfers.

## [3:35 - 4:00] Application Interfaces
Now let me briefly show you the application interfaces. On the left side of my screen is the consumer interface where users can browse and interact with photos. On the right side is the creator interface with additional features for uploading photos. These interfaces are served by the same backend API but with different permission levels, which helps with maintainability and scaling.

## [4:00 - 4:30] Scaling and Monitoring
Let's look at the scaling configuration in Azure. I've set up autoscale rules based on CPU usage and request count thresholds. When traffic increases, Azure automatically provisions additional instances up to the limit I've defined. Here in the monitoring section, you can see metrics for our application including response times, memory usage, and request counts. I've also configured alerts to notify me if any issues arise or if we're approaching resource limits.

## [4:30 - 4:50] Cost Management
An important aspect of cloud deployment is cost management. Here I've set up cost analysis and budgets to track spending. By using the right combination of services and tiers, I've optimized the infrastructure for both performance and cost. For example, the CDN reduces load on our app servers, while Blob Storage lifecycle policies automatically move less-accessed content to cheaper storage tiers.

## [4:50 - 5:00] Conclusion
That completes my demonstration of InstaShare's cloud infrastructure on Azure. I've shown you the database configuration, storage setup, deployment process using Git, networking, scaling capabilities, and monitoring. This implementation successfully delivers a scalable, maintainable photo-sharing platform using modern cloud-native principles.
