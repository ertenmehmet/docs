
---
title: "getAppSecSelectableHostnames"
title_tag: "akamai.getAppSecSelectableHostnames"
meta_desc: "Documentation for the akamai.getAppSecSelectableHostnames function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use the `akamai.getAppSecSelectableHostnames` data source to retrieve the list of hostnames that may be protected under a given security configuration. You can specify the list to be retrieved either by supplying the name of a security configuration, or by supplying a group ID and contract ID.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Akamai = Pulumi.Akamai;

class MyStack : Stack
{
    public MyStack()
    {
        var configuration = Output.Create(Akamai.GetAppSecConfiguration.InvokeAsync(new Akamai.GetAppSecConfigurationArgs
        {
            Name = @var.Security_configuration,
        }));
        var selectableHostnamesAppSecSelectableHostnames = configuration.Apply(configuration => Output.Create(Akamai.GetAppSecSelectableHostnames.InvokeAsync(new Akamai.GetAppSecSelectableHostnamesArgs
        {
            ConfigId = configuration.ConfigId,
        })));
        this.SelectableHostnames = selectableHostnamesAppSecSelectableHostnames.Apply(selectableHostnamesAppSecSelectableHostnames => selectableHostnamesAppSecSelectableHostnames.Hostnames);
        this.SelectableHostnamesJson = selectableHostnamesAppSecSelectableHostnames.Apply(selectableHostnamesAppSecSelectableHostnames => selectableHostnamesAppSecSelectableHostnames.HostnamesJson);
        this.SelectableHostnamesOutputText = selectableHostnamesAppSecSelectableHostnames.Apply(selectableHostnamesAppSecSelectableHostnames => selectableHostnamesAppSecSelectableHostnames.OutputText);
        var selectableHostnamesForCreateConfigurationAppSecSelectableHostnames = Output.Create(Akamai.GetAppSecSelectableHostnames.InvokeAsync(new Akamai.GetAppSecSelectableHostnamesArgs
        {
            Contractid = @var.Contractid,
            Groupid = @var.Groupid,
        }));
        this.SelectableHostnamesForCreateConfiguration = selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.Apply(selectableHostnamesForCreateConfigurationAppSecSelectableHostnames => selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.Hostnames);
        this.SelectableHostnamesForCreateConfigurationJson = selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.Apply(selectableHostnamesForCreateConfigurationAppSecSelectableHostnames => selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.HostnamesJson);
        this.SelectableHostnamesForCreateConfigurationOutputText = selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.Apply(selectableHostnamesForCreateConfigurationAppSecSelectableHostnames => selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.OutputText);
    }

    [Output("selectableHostnames")]
    public Output<string> SelectableHostnames { get; set; }
    [Output("selectableHostnamesJson")]
    public Output<string> SelectableHostnamesJson { get; set; }
    [Output("selectableHostnamesOutputText")]
    public Output<string> SelectableHostnamesOutputText { get; set; }
    [Output("selectableHostnamesForCreateConfiguration")]
    public Output<string> SelectableHostnamesForCreateConfiguration { get; set; }
    [Output("selectableHostnamesForCreateConfigurationJson")]
    public Output<string> SelectableHostnamesForCreateConfigurationJson { get; set; }
    [Output("selectableHostnamesForCreateConfigurationOutputText")]
    public Output<string> SelectableHostnamesForCreateConfigurationOutputText { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-akamai/sdk/v2/go/akamai"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := _var.Security_configuration
		configuration, err := akamai.LookupAppSecConfiguration(ctx, &akamai.LookupAppSecConfigurationArgs{
			Name: &opt0,
		}, nil)
		if err != nil {
			return err
		}
		opt1 := configuration.ConfigId
		selectableHostnamesAppSecSelectableHostnames, err := akamai.GetAppSecSelectableHostnames(ctx, &akamai.GetAppSecSelectableHostnamesArgs{
			ConfigId: &opt1,
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("selectableHostnames", selectableHostnamesAppSecSelectableHostnames.Hostnames)
		ctx.Export("selectableHostnamesJson", selectableHostnamesAppSecSelectableHostnames.HostnamesJson)
		ctx.Export("selectableHostnamesOutputText", selectableHostnamesAppSecSelectableHostnames.OutputText)
		opt2 := _var.Contractid
		opt3 := _var.Groupid
		selectableHostnamesForCreateConfigurationAppSecSelectableHostnames, err := akamai.GetAppSecSelectableHostnames(ctx, &akamai.GetAppSecSelectableHostnamesArgs{
			Contractid: &opt2,
			Groupid:    &opt3,
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("selectableHostnamesForCreateConfiguration", selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.Hostnames)
		ctx.Export("selectableHostnamesForCreateConfigurationJson", selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.HostnamesJson)
		ctx.Export("selectableHostnamesForCreateConfigurationOutputText", selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.OutputText)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_akamai as akamai

configuration = akamai.get_app_sec_configuration(name=var["security_configuration"])
selectable_hostnames_app_sec_selectable_hostnames = akamai.get_app_sec_selectable_hostnames(config_id=configuration.config_id)
pulumi.export("selectableHostnames", selectable_hostnames_app_sec_selectable_hostnames.hostnames)
pulumi.export("selectableHostnamesJson", selectable_hostnames_app_sec_selectable_hostnames.hostnames_json)
pulumi.export("selectableHostnamesOutputText", selectable_hostnames_app_sec_selectable_hostnames.output_text)
selectable_hostnames_for_create_configuration_app_sec_selectable_hostnames = akamai.get_app_sec_selectable_hostnames(contractid=var["contractid"],
    groupid=var["groupid"])
pulumi.export("selectableHostnamesForCreateConfiguration", selectable_hostnames_for_create_configuration_app_sec_selectable_hostnames.hostnames)
pulumi.export("selectableHostnamesForCreateConfigurationJson", selectable_hostnames_for_create_configuration_app_sec_selectable_hostnames.hostnames_json)
pulumi.export("selectableHostnamesForCreateConfigurationOutputText", selectable_hostnames_for_create_configuration_app_sec_selectable_hostnames.output_text)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as akamai from "@pulumi/akamai";

const configuration = akamai.getAppSecConfiguration({
    name: _var.security_configuration,
});
const selectableHostnamesAppSecSelectableHostnames = configuration.then(configuration => akamai.getAppSecSelectableHostnames({
    configId: configuration.configId,
}));
export const selectableHostnames = selectableHostnamesAppSecSelectableHostnames.then(selectableHostnamesAppSecSelectableHostnames => selectableHostnamesAppSecSelectableHostnames.hostnames);
export const selectableHostnamesJson = selectableHostnamesAppSecSelectableHostnames.then(selectableHostnamesAppSecSelectableHostnames => selectableHostnamesAppSecSelectableHostnames.hostnamesJson);
export const selectableHostnamesOutputText = selectableHostnamesAppSecSelectableHostnames.then(selectableHostnamesAppSecSelectableHostnames => selectableHostnamesAppSecSelectableHostnames.outputText);
const selectableHostnamesForCreateConfigurationAppSecSelectableHostnames = akamai.getAppSecSelectableHostnames({
    contractid: _var.contractid,
    groupid: _var.groupid,
});
export const selectableHostnamesForCreateConfiguration = selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.then(selectableHostnamesForCreateConfigurationAppSecSelectableHostnames => selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.hostnames);
export const selectableHostnamesForCreateConfigurationJson = selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.then(selectableHostnamesForCreateConfigurationAppSecSelectableHostnames => selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.hostnamesJson);
export const selectableHostnamesForCreateConfigurationOutputText = selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.then(selectableHostnamesForCreateConfigurationAppSecSelectableHostnames => selectableHostnamesForCreateConfigurationAppSecSelectableHostnames.outputText);
```


{{< /example >}}





{{% /examples %}}




## Using getAppSecSelectableHostnames {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getAppSecSelectableHostnames<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetAppSecSelectableHostnamesArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetAppSecSelectableHostnamesResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_app_sec_selectable_hostnames(</span><span class="nx">active_in_production</span><span class="p">:</span> <span class="nx">Optional[bool]</span> = None<span class="p">,</span>
                                     <span class="nx">active_in_staging</span><span class="p">:</span> <span class="nx">Optional[bool]</span> = None<span class="p">,</span>
                                     <span class="nx">config_id</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">,</span>
                                     <span class="nx">contractid</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                                     <span class="nx">groupid</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">,</span>
                                     <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetAppSecSelectableHostnamesResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAppSecSelectableHostnames<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetAppSecSelectableHostnamesArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetAppSecSelectableHostnamesResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetAppSecSelectableHostnames` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetAppSecSelectableHostnames </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetAppSecSelectableHostnamesResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetAppSecSelectableHostnamesArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="activeinproduction_csharp">
<a href="#activeinproduction_csharp" style="color: inherit; text-decoration: inherit;">Active<wbr>In<wbr>Production</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="activeinstaging_csharp">
<a href="#activeinstaging_csharp" style="color: inherit; text-decoration: inherit;">Active<wbr>In<wbr>Staging</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="configid_csharp">
<a href="#configid_csharp" style="color: inherit; text-decoration: inherit;">Config<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The ID of the security configuration to use.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="contractid_csharp">
<a href="#contractid_csharp" style="color: inherit; text-decoration: inherit;">Contractid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the contract to use.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="groupid_csharp">
<a href="#groupid_csharp" style="color: inherit; text-decoration: inherit;">Groupid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The ID of the group to use.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="activeinproduction_go">
<a href="#activeinproduction_go" style="color: inherit; text-decoration: inherit;">Active<wbr>In<wbr>Production</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="activeinstaging_go">
<a href="#activeinstaging_go" style="color: inherit; text-decoration: inherit;">Active<wbr>In<wbr>Staging</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="configid_go">
<a href="#configid_go" style="color: inherit; text-decoration: inherit;">Config<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The ID of the security configuration to use.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="contractid_go">
<a href="#contractid_go" style="color: inherit; text-decoration: inherit;">Contractid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the contract to use.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="groupid_go">
<a href="#groupid_go" style="color: inherit; text-decoration: inherit;">Groupid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The ID of the group to use.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="activeinproduction_nodejs">
<a href="#activeinproduction_nodejs" style="color: inherit; text-decoration: inherit;">active<wbr>In<wbr>Production</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="activeinstaging_nodejs">
<a href="#activeinstaging_nodejs" style="color: inherit; text-decoration: inherit;">active<wbr>In<wbr>Staging</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="configid_nodejs">
<a href="#configid_nodejs" style="color: inherit; text-decoration: inherit;">config<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The ID of the security configuration to use.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="contractid_nodejs">
<a href="#contractid_nodejs" style="color: inherit; text-decoration: inherit;">contractid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the contract to use.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="groupid_nodejs">
<a href="#groupid_nodejs" style="color: inherit; text-decoration: inherit;">groupid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The ID of the group to use.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="active_in_production_python">
<a href="#active_in_production_python" style="color: inherit; text-decoration: inherit;">active_<wbr>in_<wbr>production</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="active_in_staging_python">
<a href="#active_in_staging_python" style="color: inherit; text-decoration: inherit;">active_<wbr>in_<wbr>staging</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="config_id_python">
<a href="#config_id_python" style="color: inherit; text-decoration: inherit;">config_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The ID of the security configuration to use.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="contractid_python">
<a href="#contractid_python" style="color: inherit; text-decoration: inherit;">contractid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the contract to use.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="groupid_python">
<a href="#groupid_python" style="color: inherit; text-decoration: inherit;">groupid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The ID of the group to use.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getAppSecSelectableHostnames Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="hostnames_csharp">
<a href="#hostnames_csharp" style="color: inherit; text-decoration: inherit;">Hostnames</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}The list of selectable hostnames.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="hostnamesjson_csharp">
<a href="#hostnamesjson_csharp" style="color: inherit; text-decoration: inherit;">Hostnames<wbr>Json</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The list of selectable hostnames in json format.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputtext_csharp">
<a href="#outputtext_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>Text</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A tabular display of the selectable hostnames showing the name and config_id of the security configuration under which the host is protected in production, or '-' if the host is not protected in production.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="activeinproduction_csharp">
<a href="#activeinproduction_csharp" style="color: inherit; text-decoration: inherit;">Active<wbr>In<wbr>Production</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="activeinstaging_csharp">
<a href="#activeinstaging_csharp" style="color: inherit; text-decoration: inherit;">Active<wbr>In<wbr>Staging</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="configid_csharp">
<a href="#configid_csharp" style="color: inherit; text-decoration: inherit;">Config<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="contractid_csharp">
<a href="#contractid_csharp" style="color: inherit; text-decoration: inherit;">Contractid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupid_csharp">
<a href="#groupid_csharp" style="color: inherit; text-decoration: inherit;">Groupid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="hostnames_go">
<a href="#hostnames_go" style="color: inherit; text-decoration: inherit;">Hostnames</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of selectable hostnames.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="hostnamesjson_go">
<a href="#hostnamesjson_go" style="color: inherit; text-decoration: inherit;">Hostnames<wbr>Json</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The list of selectable hostnames in json format.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputtext_go">
<a href="#outputtext_go" style="color: inherit; text-decoration: inherit;">Output<wbr>Text</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A tabular display of the selectable hostnames showing the name and config_id of the security configuration under which the host is protected in production, or '-' if the host is not protected in production.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="activeinproduction_go">
<a href="#activeinproduction_go" style="color: inherit; text-decoration: inherit;">Active<wbr>In<wbr>Production</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="activeinstaging_go">
<a href="#activeinstaging_go" style="color: inherit; text-decoration: inherit;">Active<wbr>In<wbr>Staging</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="configid_go">
<a href="#configid_go" style="color: inherit; text-decoration: inherit;">Config<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="contractid_go">
<a href="#contractid_go" style="color: inherit; text-decoration: inherit;">Contractid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupid_go">
<a href="#groupid_go" style="color: inherit; text-decoration: inherit;">Groupid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="hostnames_nodejs">
<a href="#hostnames_nodejs" style="color: inherit; text-decoration: inherit;">hostnames</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The list of selectable hostnames.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="hostnamesjson_nodejs">
<a href="#hostnamesjson_nodejs" style="color: inherit; text-decoration: inherit;">hostnames<wbr>Json</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The list of selectable hostnames in json format.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputtext_nodejs">
<a href="#outputtext_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>Text</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A tabular display of the selectable hostnames showing the name and config_id of the security configuration under which the host is protected in production, or '-' if the host is not protected in production.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="activeinproduction_nodejs">
<a href="#activeinproduction_nodejs" style="color: inherit; text-decoration: inherit;">active<wbr>In<wbr>Production</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="activeinstaging_nodejs">
<a href="#activeinstaging_nodejs" style="color: inherit; text-decoration: inherit;">active<wbr>In<wbr>Staging</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="configid_nodejs">
<a href="#configid_nodejs" style="color: inherit; text-decoration: inherit;">config<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="contractid_nodejs">
<a href="#contractid_nodejs" style="color: inherit; text-decoration: inherit;">contractid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupid_nodejs">
<a href="#groupid_nodejs" style="color: inherit; text-decoration: inherit;">groupid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="hostnames_python">
<a href="#hostnames_python" style="color: inherit; text-decoration: inherit;">hostnames</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}The list of selectable hostnames.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="hostnames_json_python">
<a href="#hostnames_json_python" style="color: inherit; text-decoration: inherit;">hostnames_<wbr>json</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The list of selectable hostnames in json format.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="output_text_python">
<a href="#output_text_python" style="color: inherit; text-decoration: inherit;">output_<wbr>text</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A tabular display of the selectable hostnames showing the name and config_id of the security configuration under which the host is protected in production, or '-' if the host is not protected in production.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="active_in_production_python">
<a href="#active_in_production_python" style="color: inherit; text-decoration: inherit;">active_<wbr>in_<wbr>production</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="active_in_staging_python">
<a href="#active_in_staging_python" style="color: inherit; text-decoration: inherit;">active_<wbr>in_<wbr>staging</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="config_id_python">
<a href="#config_id_python" style="color: inherit; text-decoration: inherit;">config_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="contractid_python">
<a href="#contractid_python" style="color: inherit; text-decoration: inherit;">contractid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupid_python">
<a href="#groupid_python" style="color: inherit; text-decoration: inherit;">groupid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-akamai">https://github.com/pulumi/pulumi-akamai</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`akamai` Terraform Provider](https://github.com/akamai/terraform-provider-akamai).{{% /md %}}</dd>
</dl>

