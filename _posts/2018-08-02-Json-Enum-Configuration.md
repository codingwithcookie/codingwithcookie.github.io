---
layout: post
title:  "ASP.NET Core Json Enum Configuration"
date:   2018-08-02 00:00:00 -0800
categories: 
---

I'm working on a project which returns data back as json from a ASP.NET Core application. Part of this data is an enum and would return the interget index by default. However, that's not helpful and I want it to return the string of the enum and not the index.

By adding the JsonOptions I'm able to override the default behavior.
<code>.AddJsonOptions(opt =&gt; { opt.SerializerSettings.Converters.Add(new Newtonsoft.Json.Converters.StringEnumConverter()); })</code>
<h2>Orgiginal Code: (Startup.cs)</h2><code>// This method gets called by the runtime. Use this method to add services to the container.
public void ConfigureServices(IServiceCollection services)
{
services.AddMvc();
}</code>
<h2>Updated Code: (Startup.cs)</h2><code>// This method gets called by the runtime. Use this method to add services to the container.
public void ConfigureServices(IServiceCollection services)
{
services.AddMvc().AddJsonOptions(opt =&gt; { opt.SerializerSettings.Converters.Add(new Newtonsoft.Json.Converters.StringEnumConverter()); });
}</code>
