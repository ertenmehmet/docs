
---
title: "WorkloadNetworkPublicIP"
title_tag: "azure-native.avs.WorkloadNetworkPublicIP"
meta_desc: "Documentation for the azure-native.avs.WorkloadNetworkPublicIP resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

NSX Public IP Block
API Version: 2021-06-01.

{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}


### WorkloadNetworks_CreatePublicIP


{{< example csharp >}}

```csharp
using Pulumi;
using AzureNative = Pulumi.AzureNative;

class MyStack : Stack
{
    public MyStack()
    {
        var workloadNetworkPublicIP = new AzureNative.AVS.WorkloadNetworkPublicIP("workloadNetworkPublicIP", new AzureNative.AVS.WorkloadNetworkPublicIPArgs
        {
            DisplayName = "publicIP1",
            NumberOfPublicIPs = 32,
            PrivateCloudName = "cloud1",
            PublicIPId = "publicIP1",
            ResourceGroupName = "group1",
        });
    }

}

```


{{< /example >}}


{{< example go >}}


```go
package main

import (
	avs "github.com/pulumi/pulumi-azure-native/sdk/go/azure/avs"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := avs.NewWorkloadNetworkPublicIP(ctx, "workloadNetworkPublicIP", &avs.WorkloadNetworkPublicIPArgs{
			DisplayName:       pulumi.String("publicIP1"),
			NumberOfPublicIPs: pulumi.Float64(32),
			PrivateCloudName:  pulumi.String("cloud1"),
			PublicIPId:        pulumi.String("publicIP1"),
			ResourceGroupName: pulumi.String("group1"),
		})
		if err != nil {
			return err
		}
		return nil
	})
}

```


{{< /example >}}


{{< example python >}}


```python
import pulumi
import pulumi_azure_native as azure_native

workload_network_public_ip = azure_native.avs.WorkloadNetworkPublicIP("workloadNetworkPublicIP",
    display_name="publicIP1",
    number_of_public_ips=32,
    private_cloud_name="cloud1",
    public_ip_id="publicIP1",
    resource_group_name="group1")

```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure_native from "@pulumi/azure-native";

const workloadNetworkPublicIP = new azure_native.avs.WorkloadNetworkPublicIP("workloadNetworkPublicIP", {
    displayName: "publicIP1",
    numberOfPublicIPs: 32,
    privateCloudName: "cloud1",
    publicIPId: "publicIP1",
    resourceGroupName: "group1",
});

```


{{< /example >}}





{{% /examples %}}




## Create a WorkloadNetworkPublicIP Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">WorkloadNetworkPublicIP</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">WorkloadNetworkPublicIPArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@overload</span>
<span class="k">def </span><span class="nx">WorkloadNetworkPublicIP</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
                            <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">,</span>
                            <span class="nx">display_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                            <span class="nx">number_of_public_ips</span><span class="p">:</span> <span class="nx">Optional[float]</span> = None<span class="p">,</span>
                            <span class="nx">private_cloud_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                            <span class="nx">public_ip_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                            <span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span>
<span class=nd>@overload</span>
<span class="k">def </span><span class="nx">WorkloadNetworkPublicIP</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
                            <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">WorkloadNetworkPublicIPArgs</a></span><span class="p">,</span>
                            <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewWorkloadNetworkPublicIP</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">WorkloadNetworkPublicIPArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">WorkloadNetworkPublicIP</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">WorkloadNetworkPublicIP</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">,</span> <span class="nx"><a href="#inputs">WorkloadNetworkPublicIPArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>The unique name of the resource.</dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">WorkloadNetworkPublicIPArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

{{% choosable language python %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>The unique name of the resource.</dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">WorkloadNetworkPublicIPArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">ResourceOptions</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties"><dt
        class="property-optional" title="Optional">
        <span>ctx</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span>
    </dt>
    <dd>Context object for the current deployment.</dd><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>The unique name of the resource.</dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">WorkloadNetworkPublicIPArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>The unique name of the resource.</dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">WorkloadNetworkPublicIPArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

## WorkloadNetworkPublicIP Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Architecture and Concepts docs.

### Inputs

The WorkloadNetworkPublicIP resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="privatecloudname_csharp">
<a href="#privatecloudname_csharp" style="color: inherit; text-decoration: inherit;">Private<wbr>Cloud<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the private cloud{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="displayname_csharp">
<a href="#displayname_csharp" style="color: inherit; text-decoration: inherit;">Display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Display name of the Public IP Block.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="numberofpublicips_csharp">
<a href="#numberofpublicips_csharp" style="color: inherit; text-decoration: inherit;">Number<wbr>Of<wbr>Public<wbr>IPs</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">double</span>
    </dt>
    <dd>{{% md %}}Number of Public IPs requested.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="publicipid_csharp">
<a href="#publicipid_csharp" style="color: inherit; text-decoration: inherit;">Public<wbr>IPId</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}NSX Public IP Block identifier. Generally the same as the Public IP Block's display name{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="privatecloudname_go">
<a href="#privatecloudname_go" style="color: inherit; text-decoration: inherit;">Private<wbr>Cloud<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the private cloud{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="displayname_go">
<a href="#displayname_go" style="color: inherit; text-decoration: inherit;">Display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Display name of the Public IP Block.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="numberofpublicips_go">
<a href="#numberofpublicips_go" style="color: inherit; text-decoration: inherit;">Number<wbr>Of<wbr>Public<wbr>IPs</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">float64</span>
    </dt>
    <dd>{{% md %}}Number of Public IPs requested.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="publicipid_go">
<a href="#publicipid_go" style="color: inherit; text-decoration: inherit;">Public<wbr>IPId</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}NSX Public IP Block identifier. Generally the same as the Public IP Block's display name{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="privatecloudname_nodejs">
<a href="#privatecloudname_nodejs" style="color: inherit; text-decoration: inherit;">private<wbr>Cloud<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the private cloud{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="displayname_nodejs">
<a href="#displayname_nodejs" style="color: inherit; text-decoration: inherit;">display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Display name of the Public IP Block.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="numberofpublicips_nodejs">
<a href="#numberofpublicips_nodejs" style="color: inherit; text-decoration: inherit;">number<wbr>Of<wbr>Public<wbr>IPs</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Number of Public IPs requested.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="publicipid_nodejs">
<a href="#publicipid_nodejs" style="color: inherit; text-decoration: inherit;">public<wbr>IPId</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}NSX Public IP Block identifier. Generally the same as the Public IP Block's display name{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="private_cloud_name_python">
<a href="#private_cloud_name_python" style="color: inherit; text-decoration: inherit;">private_<wbr>cloud_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the private cloud{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="display_name_python">
<a href="#display_name_python" style="color: inherit; text-decoration: inherit;">display_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Display name of the Public IP Block.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="number_of_public_ips_python">
<a href="#number_of_public_ips_python" style="color: inherit; text-decoration: inherit;">number_<wbr>of_<wbr>public_<wbr>ips</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of Public IPs requested.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="public_ip_id_python">
<a href="#public_ip_id_python" style="color: inherit; text-decoration: inherit;">public_<wbr>ip_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}NSX Public IP Block identifier. Generally the same as the Public IP Block's display name{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the WorkloadNetworkPublicIP resource produces the following output properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioningstate_csharp">
<a href="#provisioningstate_csharp" style="color: inherit; text-decoration: inherit;">Provisioning<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provisioning state{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="publicipblock_csharp">
<a href="#publicipblock_csharp" style="color: inherit; text-decoration: inherit;">Public<wbr>IPBlock</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}CIDR Block of the Public IP Block.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_csharp">
<a href="#type_csharp" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource type.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioningstate_go">
<a href="#provisioningstate_go" style="color: inherit; text-decoration: inherit;">Provisioning<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provisioning state{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="publicipblock_go">
<a href="#publicipblock_go" style="color: inherit; text-decoration: inherit;">Public<wbr>IPBlock</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}CIDR Block of the Public IP Block.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_go">
<a href="#type_go" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource type.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioningstate_nodejs">
<a href="#provisioningstate_nodejs" style="color: inherit; text-decoration: inherit;">provisioning<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provisioning state{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="publicipblock_nodejs">
<a href="#publicipblock_nodejs" style="color: inherit; text-decoration: inherit;">public<wbr>IPBlock</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}CIDR Block of the Public IP Block.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_nodejs">
<a href="#type_nodejs" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource type.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Resource name.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioning_state_python">
<a href="#provisioning_state_python" style="color: inherit; text-decoration: inherit;">provisioning_<wbr>state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provisioning state{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="public_ip_block_python">
<a href="#public_ip_block_python" style="color: inherit; text-decoration: inherit;">public_<wbr>ip_<wbr>block</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}CIDR Block of the Public IP Block.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_python">
<a href="#type_python" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Resource type.{{% /md %}}</dd></dl>
{{% /choosable %}}






## Import


An existing resource can be imported using its type token, name, and identifier, e.g.

```sh
$ pulumi import azure-native:avs:WorkloadNetworkPublicIP publicIP1 /subscriptions/{subscription-id}/resourceGroups/group1/providers/Microsoft.AVS/privateClouds/cloud1/workloadNetworks/default/publicIPs/publicIP1 
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>

