# Broken Access Control

Broken Access Control is a critical security vulnerability that occurs when an application doesn't properly enforce restrictions on what authenticated users are allowed to do. This can result in unauthorized access to certain functionalities, data, or resources within the application. Essentially, it means that users are able to bypass the intended access controls and perform actions they shouldn't be allowed to perform.



#  Broken access control vulnerabilities examples

1. **Vertical Privilege Escalation**:
   - **Example**: A regular user is able to access administrative functions by manipulating a URL parameter.

2. **Horizontal Privilege Escalation**:
   - **Example**: User A is able to access or modify data belonging to User B due to insufficient session isolation.

3. **Direct Object References**:
   - **Example**: Changing a URL parameter to access another user's profile or private data that should not be accessible.

4. **Insecure Access to APIs**:
   - **Example**: An API endpoint doesn't require proper authentication, allowing unauthorized users to retrieve sensitive information.

5. **Insecure Direct Object References (IDOR)**:
   - **Example**: Manipulating parameters to access files or records that aren't intended for public access, such as accessing another user's invoice by changing the invoice ID in the URL.

6. **Missing Function Level Access Control**:
   - **Example**: A hidden functionality accessible via a URL that wasn't properly protected, allowing unauthorized users to perform specific actions.

7. **Unprotected URL Paths**:
   - **Example**: Failing to enforce access controls on certain URL paths, allowing unauthorized access to certain resources.

8. **Privilege Escalation via Parameter Tampering**:
   - **Example**: Changing a numeric value in the URL to manipulate the scope of a user's access, such as changing a "role" parameter from "user" to "admin."

9. **Insecure State Transitions**:
   - **Example**: An application doesn't properly check the user's current state or context, allowing them to perform actions they shouldn't be able to based on their current state.

10. **Overly Permissive Access Controls**:
    - **Example**: Giving users broader access privileges than necessary due to misconfigured roles or groups.

11. **Insecure Business Logic**:
    - **Example**: Exploiting flaws in the application's logic to perform unauthorized actions, such as skipping a required step in a workflow.

12. **Predictable Resource Locations**:
    - **Example**: An attacker can guess the URL of a sensitive resource due to a predictable naming convention.

13. **Insecure Cross-Account Access**:
    - **Example**: In a multi-tenant environment, one user gains access to another user's resources because of misconfigured access controls.

14. **Insecure Access Control Defaults**:
    - **Example**: Default settings provide broader access than necessary, and administrators fail to customize them.

<br/>

> **Note**
You can read more about the vulnerability at the [Portwigger Website](https://portswigger.net/web-security/access-control#:~:text=Broken%20access%20control%20vulnerabilities%20exist,to%20be%20able%20to%20access.)

# Lab

As Example on the vulnerability, we will solve this Lab: [Unprotected admin functionality](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality)

<p align="center">
<img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg5q8LF-tEDDk5tryh5jiI-w-zDLzJzgcgN1v5vqlarTAKh5jiwctaLl7quBCvbRAEOzsDNhuk9_ytOIBtGr1ABKL6YPKbhusNVLwObYAT6v6jMpFy93vPzR38I-D8iEOE3jXs6q2YzjFLk7a2ObSdRMrGLdUqKU1z57UX55EJHYNAve8Ftu1Oiz9uDyBY/s1382/1.PNG" alt="" height="300" >
</p>

To solve this lab, you must delete a user named "carlos"
After you click on "ACCESS THE LAB", we browse the site to try to get the admin panel, but we only find the home page and the account page that needs a username and password .
In this case, we go to ``/robots.txt`` file. in order to see the pages that are blocked from search engines. We may find the admin panel on of it. <br>
> **Note**
 It is a plain text file in which some simple code is placed to prevent crawling of certain pages that we do not want to appear in search engines. Thus, reducing the amount of data or pages to be tracked by search engine spiders, and consequently, the site is quickly indexed on search engines. <br/> You can access the /robots.txt file by adding it directly after the link

<br/>

 <p align="center">
<img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgEC4MNA3rqBjmd8FIgk57bowXFjq0IKN0RSnJt3Ce-Nx81pY3NPbljalZPCOzyW0N7yOH_Yx5imwj_OP6bEEb1TaeuxRHaJdzAIgLr8m-YPULmvgZWG4joCV0f6sLJT9ziwOgseWDiCy2KEqfn1C59le2U7FxD-uKq0SqVqLnuZmmQX4LGzzJIEoCZOAc/s1302/2.PNG" alt="" height="300" >
</p>

+ Great! We have found the admin panel at: ``/administrator-panel`` . Let's go through it by adding it right after the domain .

<br/>

 <p align="center">
<img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg6Fob-MzuUc8m7_HpbjPdKu0BW9ZTBZYBKYn6bY9F_5rAsFLs8EXvyHr-Vc7Js07ZkdAEMC9ZkfJbRVmJCYaRQvmKs9IRb4tahUrk1ggzgjwzAbDobYCp6cdExG35IIt78Hz9lvBxsliM23sXXt3mRnXXixAUsMp3ncK434yY7sC_xj7cwWSORngd7peA/s1431/3.PNG" alt="" height="300" >
</p>

+ Great, we can now delete the required user.

 <br/>
 
 <p align="center">
<img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjwa0sWDqDHwj1jvhwlu6AMzVYFRK904lMaJEGYthGZ7xRevJhCYwLTO2ZfgjPVysj0cLjyqd4mE7VPvqLdhXeRvRPilw6Vyqw37W4anG3uhX4hPLJjali1jDGhdha717UjAzSUrO6UBqJaKHlYuiKglIkXRAY4a7I6gc8zarS1s6D3AYiRL5EuUYk9U8w/s1670/4.PNG" alt="" height="300" >
</p>

 <br/>

The challenge was successfully solved, and this is a very simple example of the Broken Access Control vulnerability. Solve more labs on the [Portwigger Website](https://portswigger.net/web-security/all-labs#access-control-vulnerabilities)










































