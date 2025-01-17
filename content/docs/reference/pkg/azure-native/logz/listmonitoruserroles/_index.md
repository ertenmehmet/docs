
---
title: "listMonitorUserRoles"
title_tag: "azure-native.logz.listMonitorUserRoles"
meta_desc: "Documentation for the azure-native.logz.listMonitorUserRoles function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Response for list of user's role for Logz.io account.
API Version: 2020-10-01.




## Using listMonitorUserRoles {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>listMonitorUserRoles<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">ListMonitorUserRolesArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">ListMonitorUserRolesResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>list_monitor_user_roles(</span><span class="nx">email_address</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                            <span class="nx">monitor_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                            <span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                            <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> ListMonitorUserRolesResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>ListMonitorUserRoles<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">ListMonitorUserRolesArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">ListMonitorUserRolesResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `ListMonitorUserRoles` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">ListMonitorUserRoles </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">ListMonitorUserRolesResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">ListMonitorUserRolesArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="monitorname_csharp">
<a href="#monitorname_csharp" style="color: inherit; text-decoration: inherit;">Monitor<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Monitor resource name{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="emailaddress_csharp">
<a href="#emailaddress_csharp" style="color: inherit; text-decoration: inherit;">Email<wbr>Address</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the user used by Logz for contacting them if needed{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="monitorname_go">
<a href="#monitorname_go" style="color: inherit; text-decoration: inherit;">Monitor<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Monitor resource name{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="emailaddress_go">
<a href="#emailaddress_go" style="color: inherit; text-decoration: inherit;">Email<wbr>Address</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the user used by Logz for contacting them if needed{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="monitorname_nodejs">
<a href="#monitorname_nodejs" style="color: inherit; text-decoration: inherit;">monitor<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Monitor resource name{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="emailaddress_nodejs">
<a href="#emailaddress_nodejs" style="color: inherit; text-decoration: inherit;">email<wbr>Address</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the user used by Logz for contacting them if needed{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="monitor_name_python">
<a href="#monitor_name_python" style="color: inherit; text-decoration: inherit;">monitor_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Monitor resource name{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="email_address_python">
<a href="#email_address_python" style="color: inherit; text-decoration: inherit;">email_<wbr>address</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Email of the user used by Logz for contacting them if needed{{% /md %}}</dd></dl>
{{% /choosable %}}




## listMonitorUserRoles Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="nextlink_csharp">
<a href="#nextlink_csharp" style="color: inherit; text-decoration: inherit;">Next<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Link to the next set of results, if any.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="value_csharp">
<a href="#value_csharp" style="color: inherit; text-decoration: inherit;">Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#userroleresponseresponse">List&lt;Pulumi.<wbr>Azure<wbr>Native.<wbr>Logz.<wbr>Outputs.<wbr>User<wbr>Role<wbr>Response<wbr>Response&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of user roles for Logz.io account.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="nextlink_go">
<a href="#nextlink_go" style="color: inherit; text-decoration: inherit;">Next<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Link to the next set of results, if any.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="value_go">
<a href="#value_go" style="color: inherit; text-decoration: inherit;">Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#userroleresponseresponse">[]User<wbr>Role<wbr>Response<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}List of user roles for Logz.io account.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="nextlink_nodejs">
<a href="#nextlink_nodejs" style="color: inherit; text-decoration: inherit;">next<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Link to the next set of results, if any.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="value_nodejs">
<a href="#value_nodejs" style="color: inherit; text-decoration: inherit;">value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#userroleresponseresponse">User<wbr>Role<wbr>Response<wbr>Response[]</a></span>
    </dt>
    <dd>{{% md %}}List of user roles for Logz.io account.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="next_link_python">
<a href="#next_link_python" style="color: inherit; text-decoration: inherit;">next_<wbr>link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Link to the next set of results, if any.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="value_python">
<a href="#value_python" style="color: inherit; text-decoration: inherit;">value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#userroleresponseresponse">Sequence[User<wbr>Role<wbr>Response<wbr>Response]</a></span>
    </dt>
    <dd>{{% md %}}List of user roles for Logz.io account.{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="userroleresponseresponse">User<wbr>Role<wbr>Response<wbr>Response</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="role_csharp">
<a href="#role_csharp" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}User roles on configured in Logz.io account.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="role_go">
<a href="#role_go" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}User roles on configured in Logz.io account.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="role_nodejs">
<a href="#role_nodejs" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}User roles on configured in Logz.io account.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="role_python">
<a href="#role_python" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}User roles on configured in Logz.io account.{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>

