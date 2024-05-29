This repository contains the material that was covered in the Microsoft training module titled: Creating a web API with ASP.NET Core controllers. 

I was able to run the code in Visual Studio. At first I had an issue with building and testing the web API. When I ran the project, I noticed that only the HTTP request was listed on the console. So when I directed Google Chrome to my HTTPS port, it gave me the following error: 

warn: Microsoft.AspNetCore.HttpsPolicy.HttpsRedirectionMiddleware[3] Failed to determine the https port for redirect. 

I tried changing ports at first, but I could never connect to the page. 

After looking for a solution online, I found out that when multiple profiles are listed in the launchsettings.json file, by default the first listed profile will be used. So in this case, only the HTTP profile built by default was used, causing my problem. I ended up removing both the HTTP and HTTPS profiles and created the ContosoPizza profile and specified an HTTPS port. After doing this and building the project, I was able to connect to the HTTPS port and I no longer had an error message. 

The documentation that references using multiple environments: https://learn.microsoft.com/en-us/aspnet/core/fundamentals/environments?view=aspnetcore-7.0#development-and-launchsettingsjson 

I's not sure if this is the right fix for this since I'm learning this for the first time, so any feedback would be greatly appreciated. 
