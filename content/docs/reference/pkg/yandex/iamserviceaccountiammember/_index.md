
---
title: "IamServiceAccountIamMember"
title_tag: "yandex.IamServiceAccountIamMember"
meta_desc: "Documentation for the yandex.IamServiceAccountIamMember resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

When managing IAM roles, you can treat a service account either as a resource or as an identity.
This resource is used to add IAM policy bindings to a service account resource to configure permissions
that define who can edit the service account.

There are three different resources that help you manage your IAM policy for a service account.
Each of these resources is used for a different use case:

* yandex_iam_service_account_iam_policy: Authoritative. Sets the IAM policy for the service account and replaces any existing policy already attached.
* yandex_iam_service_account_iam_binding: Authoritative for a given role. Updates the IAM policy to grant a role to a list of members. Other roles within the IAM policy for the service account are preserved.
* yandex_iam_service_account_iam_member: Non-authoritative. Updates the IAM policy to grant a role to a new member. Other members for the role of the service account are preserved.

> **Note:** `yandex.IamServiceAccountIamPolicy` **cannot** be used in conjunction with `yandex.IamServiceAccountIamBinding` and `yandex.IamServiceAccountIamMember` or they will conflict over what your policy should be.

> **Note:** `yandex.IamServiceAccountIamBinding` resources **can be** used in conjunction with `yandex.IamServiceAccountIamMember` resources **only if** they do not grant privileges to the same role.

## yandex\_service\_account\_iam\_member

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as yandex from "@pulumi/yandex";

const admin_account_iam = new yandex.IamServiceAccountIamMember("admin-account-iam", {
    member: "userAccount:bar_user_id",
    role: "admin",
    serviceAccountId: "your-service-account-id",
});
```
```python
import pulumi
import pulumi_yandex as yandex

admin_account_iam = yandex.IamServiceAccountIamMember("admin-account-iam",
    member="userAccount:bar_user_id",
    role="admin",
    service_account_id="your-service-account-id")
```
```csharp
using Pulumi;
using Yandex = Pulumi.Yandex;

class MyStack : Stack
{
    public MyStack()
    {
        var admin_account_iam = new Yandex.IamServiceAccountIamMember("admin-account-iam", new Yandex.IamServiceAccountIamMemberArgs
        {
            Member = "userAccount:bar_user_id",
            Role = "admin",
            ServiceAccountId = "your-service-account-id",
        });
    }

}
```
```go
package main

import (
	"github.com/pulumi/pulumi-yandex/sdk/go/yandex"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := yandex.NewIamServiceAccountIamMember(ctx, "admin_account_iam", &yandex.IamServiceAccountIamMemberArgs{
			Member:           pulumi.String("userAccount:bar_user_id"),
			Role:             pulumi.String("admin"),
			ServiceAccountId: pulumi.String("your-service-account-id"),
		})
		if err != nil {
			return err
		}
		return nil
	})
}
```



## Create a IamServiceAccountIamMember Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">IamServiceAccountIamMember</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">IamServiceAccountIamMemberArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@overload</span>
<span class="k">def </span><span class="nx">IamServiceAccountIamMember</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
                               <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">,</span>
                               <span class="nx">member</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                               <span class="nx">role</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                               <span class="nx">service_account_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                               <span class="nx">sleep_after</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">)</span>
<span class=nd>@overload</span>
<span class="k">def </span><span class="nx">IamServiceAccountIamMember</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
                               <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">IamServiceAccountIamMemberArgs</a></span><span class="p">,</span>
                               <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewIamServiceAccountIamMember</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">IamServiceAccountIamMemberArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">IamServiceAccountIamMember</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">IamServiceAccountIamMember</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">,</span> <span class="nx"><a href="#inputs">IamServiceAccountIamMemberArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">IamServiceAccountIamMemberArgs</a></span>
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
        <span class="property-type"><a href="#inputs">IamServiceAccountIamMemberArgs</a></span>
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
        <span class="property-type"><a href="#inputs">IamServiceAccountIamMemberArgs</a></span>
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
        <span class="property-type"><a href="#inputs">IamServiceAccountIamMemberArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

## IamServiceAccountIamMember Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Architecture and Concepts docs.

### Inputs

The IamServiceAccountIamMember resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="member_csharp">
<a href="#member_csharp" style="color: inherit; text-decoration: inherit;">Member</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identity that will be granted the privilege in `role`.
Entry can have one of the following values:
* **userAccount:{user_id}**: A unique user ID that represents a specific Yandex account.
* **serviceAccount:{service_account_id}**: A unique service account ID.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_csharp">
<a href="#role_csharp" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role that should be applied. Only one
`yandex.IamServiceAccountIamBinding` can be used per role.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="serviceaccountid_csharp">
<a href="#serviceaccountid_csharp" style="color: inherit; text-decoration: inherit;">Service<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service account ID to apply a policy to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="sleepafter_csharp">
<a href="#sleepafter_csharp" style="color: inherit; text-decoration: inherit;">Sleep<wbr>After</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="member_go">
<a href="#member_go" style="color: inherit; text-decoration: inherit;">Member</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identity that will be granted the privilege in `role`.
Entry can have one of the following values:
* **userAccount:{user_id}**: A unique user ID that represents a specific Yandex account.
* **serviceAccount:{service_account_id}**: A unique service account ID.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_go">
<a href="#role_go" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role that should be applied. Only one
`yandex.IamServiceAccountIamBinding` can be used per role.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="serviceaccountid_go">
<a href="#serviceaccountid_go" style="color: inherit; text-decoration: inherit;">Service<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service account ID to apply a policy to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="sleepafter_go">
<a href="#sleepafter_go" style="color: inherit; text-decoration: inherit;">Sleep<wbr>After</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="member_nodejs">
<a href="#member_nodejs" style="color: inherit; text-decoration: inherit;">member</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identity that will be granted the privilege in `role`.
Entry can have one of the following values:
* **userAccount:{user_id}**: A unique user ID that represents a specific Yandex account.
* **serviceAccount:{service_account_id}**: A unique service account ID.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_nodejs">
<a href="#role_nodejs" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role that should be applied. Only one
`yandex.IamServiceAccountIamBinding` can be used per role.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="serviceaccountid_nodejs">
<a href="#serviceaccountid_nodejs" style="color: inherit; text-decoration: inherit;">service<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service account ID to apply a policy to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="sleepafter_nodejs">
<a href="#sleepafter_nodejs" style="color: inherit; text-decoration: inherit;">sleep<wbr>After</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="member_python">
<a href="#member_python" style="color: inherit; text-decoration: inherit;">member</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identity that will be granted the privilege in `role`.
Entry can have one of the following values:
* **userAccount:{user_id}**: A unique user ID that represents a specific Yandex account.
* **serviceAccount:{service_account_id}**: A unique service account ID.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_python">
<a href="#role_python" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The role that should be applied. Only one
`yandex.IamServiceAccountIamBinding` can be used per role.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="service_account_id_python">
<a href="#service_account_id_python" style="color: inherit; text-decoration: inherit;">service_<wbr>account_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The service account ID to apply a policy to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="sleep_after_python">
<a href="#sleep_after_python" style="color: inherit; text-decoration: inherit;">sleep_<wbr>after</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the IamServiceAccountIamMember resource produces the following output properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}



## Look up an Existing IamServiceAccountIamMember Resource {#look-up}

Get an existing IamServiceAccountIamMember resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">,</span> <span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">,</span> <span class="nx">state</span><span class="p">?:</span> <span class="nx">IamServiceAccountIamMemberState</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">IamServiceAccountIamMember</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
        <span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
        <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">,</span>
        <span class="nx">member</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
        <span class="nx">role</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
        <span class="nx">service_account_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
        <span class="nx">sleep_after</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">) -&gt;</span> IamServiceAccountIamMember</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetIamServiceAccountIamMember<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">,</span> <span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">,</span> <span class="nx">state</span><span class="p"> *</span><span class="nx">IamServiceAccountIamMemberState</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">IamServiceAccountIamMember</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">IamServiceAccountIamMember</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">,</span> <span class="nx">IamServiceAccountIamMemberState</span><span class="p">? </span><span class="nx">state<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Optional">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

The following state arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_member_csharp">
<a href="#state_member_csharp" style="color: inherit; text-decoration: inherit;">Member</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identity that will be granted the privilege in `role`.
Entry can have one of the following values:
* **userAccount:{user_id}**: A unique user ID that represents a specific Yandex account.
* **serviceAccount:{service_account_id}**: A unique service account ID.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_role_csharp">
<a href="#state_role_csharp" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role that should be applied. Only one
`yandex.IamServiceAccountIamBinding` can be used per role.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_serviceaccountid_csharp">
<a href="#state_serviceaccountid_csharp" style="color: inherit; text-decoration: inherit;">Service<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service account ID to apply a policy to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_sleepafter_csharp">
<a href="#state_sleepafter_csharp" style="color: inherit; text-decoration: inherit;">Sleep<wbr>After</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_member_go">
<a href="#state_member_go" style="color: inherit; text-decoration: inherit;">Member</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identity that will be granted the privilege in `role`.
Entry can have one of the following values:
* **userAccount:{user_id}**: A unique user ID that represents a specific Yandex account.
* **serviceAccount:{service_account_id}**: A unique service account ID.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_role_go">
<a href="#state_role_go" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role that should be applied. Only one
`yandex.IamServiceAccountIamBinding` can be used per role.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_serviceaccountid_go">
<a href="#state_serviceaccountid_go" style="color: inherit; text-decoration: inherit;">Service<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service account ID to apply a policy to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_sleepafter_go">
<a href="#state_sleepafter_go" style="color: inherit; text-decoration: inherit;">Sleep<wbr>After</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_member_nodejs">
<a href="#state_member_nodejs" style="color: inherit; text-decoration: inherit;">member</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identity that will be granted the privilege in `role`.
Entry can have one of the following values:
* **userAccount:{user_id}**: A unique user ID that represents a specific Yandex account.
* **serviceAccount:{service_account_id}**: A unique service account ID.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_role_nodejs">
<a href="#state_role_nodejs" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role that should be applied. Only one
`yandex.IamServiceAccountIamBinding` can be used per role.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_serviceaccountid_nodejs">
<a href="#state_serviceaccountid_nodejs" style="color: inherit; text-decoration: inherit;">service<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service account ID to apply a policy to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_sleepafter_nodejs">
<a href="#state_sleepafter_nodejs" style="color: inherit; text-decoration: inherit;">sleep<wbr>After</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_member_python">
<a href="#state_member_python" style="color: inherit; text-decoration: inherit;">member</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identity that will be granted the privilege in `role`.
Entry can have one of the following values:
* **userAccount:{user_id}**: A unique user ID that represents a specific Yandex account.
* **serviceAccount:{service_account_id}**: A unique service account ID.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_role_python">
<a href="#state_role_python" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The role that should be applied. Only one
`yandex.IamServiceAccountIamBinding` can be used per role.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_service_account_id_python">
<a href="#state_service_account_id_python" style="color: inherit; text-decoration: inherit;">service_<wbr>account_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The service account ID to apply a policy to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_sleep_after_python">
<a href="#state_sleep_after_python" style="color: inherit; text-decoration: inherit;">sleep_<wbr>after</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


Service account IAM member resources can be imported using the service account ID, role and member.

```sh
 $ pulumi import yandex:index/iamServiceAccountIamMember:IamServiceAccountIamMember admin-account-iam "service_account_id roles/editor foo@example.com"
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-yandex">https://github.com/pulumi/pulumi-yandex</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`yandex` Terraform Provider](https://github.com/yandex-cloud/terraform-provider-yandex).{{% /md %}}</dd>
</dl>

