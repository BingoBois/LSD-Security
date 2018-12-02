# LSD-Security
LSD Assignment regarding Secutiry
-----
1.  Define your assets 
*   Data/Database (User information)
*   Source Code (If it were to go missing)
*   Server (If it were to top working)
1.  Create a risk matrix of your project 

    (If we lost data, sine no real backup)


<table>
  <tr>
   <td>
   </td>
   <td>
Negligible
   </td>
   <td>Marginal
   </td>
   <td>Critical
   </td>
   <td>Catastrophic
   </td>
  </tr>
  <tr>
   <td>Certain
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Likely
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>(C) Stolen Data
   </td>
  </tr>
  <tr>
   <td>Possible
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>(A)Loss of Data
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Unlikely
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Rare
   </td>
   <td>
   </td>
   <td>(B)Loss of source code
   </td>
   <td>(D) Server Dies
   </td>
   <td>
   </td>
  </tr>
</table>



    (A): Loss of data; we don't have any automatic backups since it is a "school project" and don't invest into two seperate servers. We have "rare" manual backups, and "people" wouldn't really have a motive to do this to us. 


    (B): Loss of source code; we host our repository on Github, and only have local copies of the software, which might set us back a day or so of work. If github were to go down, we would guess they would have backups, so this would likely NEVER happen.


    (C): Because the Source code is public and we also have keys in a public Google Doc, potential hackers could gain access to our Database and steal user data such as Emails and hash-passwords, that could be reverse engineered thanks to the public source code.


    (D): Server Dies; if our host (Contabo) were to go out of business from one day to the other, we would have to deploy everything to a new host. We have already done this once, and it wasn't too bad (since we have everything including devops files for Kubernetes backed up).



1.  As operators: 
    1.  Try to find at least one vulnerability in the project you are operating
        1.  The team has a private google doc containing all their important keys and login informations to the project.
        1.  Uses process.env.MONGO_URL variable to login to their DB, really smart actually 
        1.  It's a long shot, but bear with us: While the team has been really smart in hiding and securing sensitive login information, the team states in their documentation, that one can request login information to the project by simply contacting them. This request can be made by clicking on the provided google link and combined with the fact that the team have also linked all of their team members gmail accounts, one could try and force them self into one of their gmail accounts and grant access to the document. 
    1.   Run OWTF or take one of the OWASP top 10 

    First tried to run [https://owtf.github.io](https://owtf.github.io/#download) manually which didn't work, then we tried running the Dockerimage([https://github.com/owtf/owtf/blob/develop/docker/Dockerfile](https://github.com/owtf/owtf/blob/develop/docker/Dockerfile) ) which didn't work because the server we used had a "too new kernel"([https://github.com/moby/moby/issues/27426](https://github.com/moby/moby/issues/27426)).


Then we tried on Ubuntu and it got stuck on building the container (no errors).

We tried following MULTIPLE guides but python seems to be missing dependencies no matter what (tornado, install utils).

We are sorry to disappoint, but the software does not work, and the guides aren't even up to date (setup script files are even wrong names).



    1.   Try to find the attack in the logs
