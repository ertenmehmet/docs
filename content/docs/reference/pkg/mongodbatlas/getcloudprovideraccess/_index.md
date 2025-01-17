
---
title: "getCloudProviderAccess"
title_tag: "mongodbatlas.getCloudProviderAccess"
meta_desc: "Documentation for the mongodbatlas.getCloudProviderAccess function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

`mongodbatlas.CloudProviderAccess` allows you to get the list of cloud provider access roles, currently only AWS is supported.

> **NOTE:** Groups and projects are synonymous terms. You may find `groupId` in the official documentation.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Mongodbatlas = Pulumi.Mongodbatlas;

class MyStack : Stack
{
    public MyStack()
    {
        var testRole = new Mongodbatlas.CloudProviderAccess("testRole", new Mongodbatlas.CloudProviderAccessArgs
        {
            ProjectId = "<PROJECT-ID>",
            ProviderName = "AWS",
        });
        var all = testRole.ProjectId.Apply(projectId => Mongodbatlas.GetCloudProviderAccess.InvokeAsync(new Mongodbatlas.GetCloudProviderAccessArgs
        {
            ProjectId = projectId,
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-mongodbatlas/sdk/v3/go/mongodbatlas"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		testRole, err := mongodbatlas.NewCloudProviderAccess(ctx, "testRole", &mongodbatlas.CloudProviderAccessArgs{
			ProjectId:    pulumi.String("<PROJECT-ID>"),
			ProviderName: pulumi.String("AWS"),
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
import pulumi_mongodbatlas as mongodbatlas

test_role = mongodbatlas.CloudProviderAccess("testRole",
    project_id="<PROJECT-ID>",
    provider_name="AWS")
all = test_role.project_id.apply(lambda project_id: mongodbatlas.get_cloud_provider_access(project_id=project_id))
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as mongodbatlas from "@pulumi/mongodbatlas";

const testRole = new mongodbatlas.CloudProviderAccess("testRole", {
    projectId: "<PROJECT-ID>",
    providerName: "AWS",
});
const all = testRole.projectId.apply(projectId => mongodbatlas.getCloudProviderAccess({
    projectId: projectId,
}));
```


{{< /example >}}





{{% /examples %}}




## Using getCloudProviderAccess {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getCloudProviderAccess<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetCloudProviderAccessArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetCloudProviderAccessResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_cloud_provider_access(</span><span class="nx">project_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                              <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetCloudProviderAccessResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupCloudProviderAccess<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">LookupCloudProviderAccessArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupCloudProviderAccessResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupCloudProviderAccess` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetCloudProviderAccess </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetCloudProviderAccessResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetCloudProviderAccessArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique ID for the project to get all Cloud Provider Access
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique ID for the project to get all Cloud Provider Access
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique ID for the project to get all Cloud Provider Access
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unique ID for the project to get all Cloud Provider Access
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getCloudProviderAccess Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="awsiamroles_csharp">
<a href="#awsiamroles_csharp" style="color: inherit; text-decoration: inherit;">Aws<wbr>Iam<wbr>Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcloudprovideraccessawsiamrole">List&lt;Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list where each represents a Cloud Provider Access Role.
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
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="awsiamroles_go">
<a href="#awsiamroles_go" style="color: inherit; text-decoration: inherit;">Aws<wbr>Iam<wbr>Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcloudprovideraccessawsiamrole">[]Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role</a></span>
    </dt>
    <dd>{{% md %}}A list where each represents a Cloud Provider Access Role.
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
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="awsiamroles_nodejs">
<a href="#awsiamroles_nodejs" style="color: inherit; text-decoration: inherit;">aws<wbr>Iam<wbr>Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcloudprovideraccessawsiamrole">Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role[]</a></span>
    </dt>
    <dd>{{% md %}}A list where each represents a Cloud Provider Access Role.
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
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="aws_iam_roles_python">
<a href="#aws_iam_roles_python" style="color: inherit; text-decoration: inherit;">aws_<wbr>iam_<wbr>roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcloudprovideraccessawsiamrole">Sequence[Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role]</a></span>
    </dt>
    <dd>{{% md %}}A list where each represents a Cloud Provider Access Role.
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
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getcloudprovideraccessawsiamrole">Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="atlasassumedroleexternalid_csharp">
<a href="#atlasassumedroleexternalid_csharp" style="color: inherit; text-decoration: inherit;">Atlas<wbr>Assumed<wbr>Role<wbr>External<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique external ID Atlas uses when assuming the IAM role in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="atlasawsaccountarn_csharp">
<a href="#atlasawsaccountarn_csharp" style="color: inherit; text-decoration: inherit;">Atlas<wbr>Aws<wbr>Account<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN associated with the Atlas AWS account used to assume IAM roles in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="authorizeddate_csharp">
<a href="#authorizeddate_csharp" style="color: inherit; text-decoration: inherit;">Authorized<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date on which this role was authorized.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="createddate_csharp">
<a href="#createddate_csharp" style="color: inherit; text-decoration: inherit;">Created<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date on which this role was created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="featureusages_csharp">
<a href="#featureusages_csharp" style="color: inherit; text-decoration: inherit;">Feature<wbr>Usages</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcloudprovideraccessawsiamrolefeatureusage">List&lt;Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role<wbr>Feature<wbr>Usage&gt;</a></span>
    </dt>
    <dd>{{% md %}}Atlas features this AWS IAM role is linked to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="iamassumedrolearn_csharp">
<a href="#iamassumedrolearn_csharp" style="color: inherit; text-decoration: inherit;">Iam<wbr>Assumed<wbr>Role<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM Role that Atlas assumes when accessing resources in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="providername_csharp">
<a href="#providername_csharp" style="color: inherit; text-decoration: inherit;">Provider<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the cloud provider. Currently limited to AWS.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="roleid_csharp">
<a href="#roleid_csharp" style="color: inherit; text-decoration: inherit;">Role<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique ID of this role.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="atlasassumedroleexternalid_go">
<a href="#atlasassumedroleexternalid_go" style="color: inherit; text-decoration: inherit;">Atlas<wbr>Assumed<wbr>Role<wbr>External<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique external ID Atlas uses when assuming the IAM role in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="atlasawsaccountarn_go">
<a href="#atlasawsaccountarn_go" style="color: inherit; text-decoration: inherit;">Atlas<wbr>Aws<wbr>Account<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN associated with the Atlas AWS account used to assume IAM roles in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="authorizeddate_go">
<a href="#authorizeddate_go" style="color: inherit; text-decoration: inherit;">Authorized<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date on which this role was authorized.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="createddate_go">
<a href="#createddate_go" style="color: inherit; text-decoration: inherit;">Created<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date on which this role was created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="featureusages_go">
<a href="#featureusages_go" style="color: inherit; text-decoration: inherit;">Feature<wbr>Usages</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcloudprovideraccessawsiamrolefeatureusage">[]Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role<wbr>Feature<wbr>Usage</a></span>
    </dt>
    <dd>{{% md %}}Atlas features this AWS IAM role is linked to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="iamassumedrolearn_go">
<a href="#iamassumedrolearn_go" style="color: inherit; text-decoration: inherit;">Iam<wbr>Assumed<wbr>Role<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM Role that Atlas assumes when accessing resources in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="providername_go">
<a href="#providername_go" style="color: inherit; text-decoration: inherit;">Provider<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the cloud provider. Currently limited to AWS.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="roleid_go">
<a href="#roleid_go" style="color: inherit; text-decoration: inherit;">Role<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique ID of this role.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="atlasassumedroleexternalid_nodejs">
<a href="#atlasassumedroleexternalid_nodejs" style="color: inherit; text-decoration: inherit;">atlas<wbr>Assumed<wbr>Role<wbr>External<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique external ID Atlas uses when assuming the IAM role in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="atlasawsaccountarn_nodejs">
<a href="#atlasawsaccountarn_nodejs" style="color: inherit; text-decoration: inherit;">atlas<wbr>Aws<wbr>Account<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN associated with the Atlas AWS account used to assume IAM roles in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="authorizeddate_nodejs">
<a href="#authorizeddate_nodejs" style="color: inherit; text-decoration: inherit;">authorized<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date on which this role was authorized.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="createddate_nodejs">
<a href="#createddate_nodejs" style="color: inherit; text-decoration: inherit;">created<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date on which this role was created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="featureusages_nodejs">
<a href="#featureusages_nodejs" style="color: inherit; text-decoration: inherit;">feature<wbr>Usages</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcloudprovideraccessawsiamrolefeatureusage">Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role<wbr>Feature<wbr>Usage[]</a></span>
    </dt>
    <dd>{{% md %}}Atlas features this AWS IAM role is linked to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="iamassumedrolearn_nodejs">
<a href="#iamassumedrolearn_nodejs" style="color: inherit; text-decoration: inherit;">iam<wbr>Assumed<wbr>Role<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM Role that Atlas assumes when accessing resources in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="providername_nodejs">
<a href="#providername_nodejs" style="color: inherit; text-decoration: inherit;">provider<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the cloud provider. Currently limited to AWS.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="roleid_nodejs">
<a href="#roleid_nodejs" style="color: inherit; text-decoration: inherit;">role<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique ID of this role.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="atlas_assumed_role_external_id_python">
<a href="#atlas_assumed_role_external_id_python" style="color: inherit; text-decoration: inherit;">atlas_<wbr>assumed_<wbr>role_<wbr>external_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique external ID Atlas uses when assuming the IAM role in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="atlas_aws_account_arn_python">
<a href="#atlas_aws_account_arn_python" style="color: inherit; text-decoration: inherit;">atlas_<wbr>aws_<wbr>account_<wbr>arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN associated with the Atlas AWS account used to assume IAM roles in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="authorized_date_python">
<a href="#authorized_date_python" style="color: inherit; text-decoration: inherit;">authorized_<wbr>date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Date on which this role was authorized.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="created_date_python">
<a href="#created_date_python" style="color: inherit; text-decoration: inherit;">created_<wbr>date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Date on which this role was created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="feature_usages_python">
<a href="#feature_usages_python" style="color: inherit; text-decoration: inherit;">feature_<wbr>usages</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcloudprovideraccessawsiamrolefeatureusage">Sequence[Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role<wbr>Feature<wbr>Usage]</a></span>
    </dt>
    <dd>{{% md %}}Atlas features this AWS IAM role is linked to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="iam_assumed_role_arn_python">
<a href="#iam_assumed_role_arn_python" style="color: inherit; text-decoration: inherit;">iam_<wbr>assumed_<wbr>role_<wbr>arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM Role that Atlas assumes when accessing resources in your AWS account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="provider_name_python">
<a href="#provider_name_python" style="color: inherit; text-decoration: inherit;">provider_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the cloud provider. Currently limited to AWS.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_id_python">
<a href="#role_id_python" style="color: inherit; text-decoration: inherit;">role_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique ID of this role.
{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getcloudprovideraccessawsiamrolefeatureusage">Get<wbr>Cloud<wbr>Provider<wbr>Access<wbr>Aws<wbr>Iam<wbr>Role<wbr>Feature<wbr>Usage</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="featureid_csharp">
<a href="#featureid_csharp" style="color: inherit; text-decoration: inherit;">Feature<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, object&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="featuretype_csharp">
<a href="#featuretype_csharp" style="color: inherit; text-decoration: inherit;">Feature<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="featureid_go">
<a href="#featureid_go" style="color: inherit; text-decoration: inherit;">Feature<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="featuretype_go">
<a href="#featuretype_go" style="color: inherit; text-decoration: inherit;">Feature<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="featureid_nodejs">
<a href="#featureid_nodejs" style="color: inherit; text-decoration: inherit;">feature<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="featuretype_nodejs">
<a href="#featuretype_nodejs" style="color: inherit; text-decoration: inherit;">feature<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="feature_id_python">
<a href="#feature_id_python" style="color: inherit; text-decoration: inherit;">feature_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="feature_type_python">
<a href="#feature_type_python" style="color: inherit; text-decoration: inherit;">feature_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-mongodbatlas">https://github.com/pulumi/pulumi-mongodbatlas</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`mongodbatlas` Terraform Provider](https://github.com/mongodb/terraform-provider-mongodbatlas).{{% /md %}}</dd>
</dl>

