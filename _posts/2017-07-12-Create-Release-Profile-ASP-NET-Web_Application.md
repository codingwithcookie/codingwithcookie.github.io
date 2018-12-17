---
layout: post
title:  "Create a release profile for an ASP.NET Web Application"
date:   2017-07-12 00:00:00 -0800
categories: Tools
---

This post will walk you through creating a release profile in your [ASP.NET Web Application](https://docs.microsoft.com/en-us/dotnet/framework/develop-web-apps-with-aspnet), which can be used for CI/CD on [VSTS](https://www.visualstudio.com/team-services/) now [Azure DevOps](https://azure.microsoft.com/en-us/services/devops/).
1. Right click on your web project and select __Publish...__  
![Right Click Publish][rightclickpublish]  
2. Then click __Custom__ as the target.  
![Select Custom][selectcustom]
3. Name the profile `Release`  
![Name the Profile][releasename]
4. Select Web Deploy Package as the Publish method.  
  * Package location of `deploy.zip`
  * And Site name of `__SiteName__`  
![Connection][connection]  
And click __Next__
5. Select your release configuration. *(I use Release which is the default.)*  
![Publish Settings][publishsettings]  
And click __Close__
6. Click __Yes__ to save the configuration you just created.
![Save Profile][save]
7. Finally, in the solution explorer, right click on the __Release.pubxml__ in the __Properties > PublishProfiles__ folder and select __Add Ignored File to Source Control...__  
![Add File to Source Control][sourcecontrol]


[rightclickpublish]: /images/release_profile/Right Click Publish.png
[selectcustom]: /images/release_profile/Select Custom.png
[releasename]: /images/release_profile/Release Name.png
[connection]: /images/release_profile/Connection.png
[publishsettings]: /images/release_profile/Publish Settings.png
[save]: /images/release_profile/Save.png
[sourcecontrol]: /images/release_profile/Add File to Source Control.png
