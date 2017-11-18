## HW5 - Configuration Management and Continuous Deployment (CSC 510)  
## Unity ID: khchoksi    ||   Name: Khantil Choksi

-----------------------------------
#### 1. Setup.yml   
[Click here to view the yml file](/setup.yml)  
Screencast for Setup:   [Click here to view Setup Screencast](https://youtu.be/6LxHgRlcvZM)

----------------------------------------
#### 2. Tasks.yml   
[Click here to view the yml file](/tasks.yml)  
Screencast for Tasks:   [Click here to view Tasks Screencast](https://youtu.be/ObfdnqWelNg)  

------------------------------------------------------------
#### Steps for running ansible and playbooks:    
 *  Install Ansible on configuration server using following commands:  
   ansible-box> $ sudo apt-add-repository ppa:ansible/ansible  
   ansible-box> $ sudo apt-get update  
   ansible-box> $ sudo apt-get install ansible    
 *  Setup inventory files and SSH keys for all nodes  
 *  Run playbook using following commands:   
      ansible-playbook setup.yml -i inventory  
      ansible-playbook tasks.yml -i inventory  
  
----------------------------------------------
### Concepts:  
#### 1. Why should developers use configuration management tools to manage their software programs? What can go wrong?    
 * In software engineering, configuration management tools provides the task of tracking and controlling changes in the software, part of the larger cross-disciplinary field of configuration management. They include revision control and the establishment of baselines. If something goes wrong, these tools can determine what was changed and who changed it. If a configuration is working well, tools can determine how to replicate it across many hosts.  
 * Configuration Management Tools helps developer for establishing, and maintaining, the consistency of a system or product, throughout its software development lifetime.   
 * These tools are basically a collection of competencies, techniques and tools; whose purpose is to ensure the consistency of the system’s requirements, functional attributes and physical properties.  
 * These tools ensure that the current design and build state of the system is known and recorded; and doesn’t rely on the tacit knowledge of the development team.  
 * For project management and audit purposes, and development activities such as debugging, configuration management tools saves the historical record of system development. For example, to know what has changed between one set of tests and the next, to help identify what could possibly be causing a fault.
 * Moreover, these tools enables developers to formally and safely record all change details. Particularly, it also records what was changed in the product, but why it was changed is also recorded.  
 * These tools ensures that accurate documentation can be produced, which truly describes delivered systems.  
 * It is also necessary to rebuild old versions of products to reproduce problems for customers, such as the military, haven’t upgraded their tools to the latest versions. For these types of upgradations, configuration management tools play an important role.  
 * Configuration tools helps developers to support product lines of software e.g. basic, gold, diamond or free / paid versions; for different types of customers.  
 * Efficient and properly built configuration management tools enable a system to be rebuilt correctly in the event of mistakes, failures and catastrophes.  
 * Different types of configuration management tools available are: 
    * VSS – Visual source safe
    * CVS- Concurrent version system  
    * Rational Clear Case  
    * SVN- Subversion  
    * Perforce  
    * TortoiseSVN  
    * IBM Rational team concert  
    * IBM Configuration management version management  

* **What can go wrong for configuration management tools:**  
 * Configuration management can seem an awful lot of effort, much of which appears to be an overhead on the development of software. However, getting these tools wrong can lead to the following:  
   * Wrong requirements being accepted  
   * Wrong design being implemented  
   * Wrong tools being used for development  
   * Wrong software being tested  
   * Wrong test suite being used / built  
   * Wrong version of software being released    
 * Any of the above can lead to huge amounts of wasted efforts, wasted money, late deliveries and that leads to dissatisfied customers. It is very important that correct product with accurate configurations are delivered to the customer.  
*Reference:* https://en.wikipedia.org/wiki/Software_configuration_management    

----------------------------------------------------------------------------------------------
#### 2. Explain the difference bewteen continuous integration, continuous delivery, and continuous deployment, in your own words.  
  **(i) Continuous Integration:**  
  * Continuous Integration means that, for each and every change committed to source repository, 
automatically build, test and analyze that software change.  
 * Developers practicing continuous integration merge their changes back to the main branch as frequent as possible. The developer's changes are validated by creating a build and running automated tests against the build. By doing so, we avoid the integration hell that usually happens, when people wait for release day to merge their changes into the release branch.  
 * Continuous integration puts a great emphasis on testing automation to check that the application is not broken whenever new commits are integrated into the main branch.  
 
 **(ii) Continuous Delivery:**   
 * Continuous Delivery ensures that a software change can be delivered and ready for use by a customer by testing in production-like environments.   
 * Software can be deployed to customers at any time with the "push of a button" (i.e. by running a deployment script).   
 * Continuous delivery is an extension of continuous integration to make sure that you can release new changes to your customers quickly in a sustainable way. On top of having automated your testing, you also have automated your release process and you can deploy your application at any point of time by clicking on a button.  
 * With continuous delivery, you can decide to release daily, weekly, fortnightly, or whatever suits our business requirements. However, if we truly want to get the benefits of continuous delivery, we should deploy to production as early as possible to make sure that you release small batches, that are easy to troubleshoot in case of a problem.
 
**(iii) Continuous Deployment:**  
 * Continuous Deployment is where incremental software changes are automatically tested, vetted, and deployed to production environments.   
 * Software is automatically deployed to customers once it passes through the continuous integration system.  
 * Continuous deployment goes one step further than continuous delivery. Every change that passes all stages of your production pipeline is directly released to your customers. There's no human intervention, and only a failed test will prevent a new change to be deployed to production.  
 * Continuous deployment is an excellent way to accelerate the feedback loop with our customers and take pressure off the team as there isn't a Release Day anymore. Developers can focus on building software, and they see their work go live minutes after we have finished working on it.    
 
*Summary:* Continuous integration is part of both continuous delivery and continuous deployment. And continuous deployment is like continuous delivery, except that releases happen automatically. Here is the graphical representation:  
![Continuous Deployment](/continuous_deployment.png)

 *Reference:* https://www.atlassian.com/continuous-delivery/ci-vs-ci-vs-cd
