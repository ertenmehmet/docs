
---
title: "getConfigMaps"
title_tag: "alicloud.sae.getConfigMaps"
meta_desc: "Documentation for the alicloud.sae.getConfigMaps function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

This data source provides the Sae Config Maps of the current Alibaba Cloud user.

> **NOTE:** Available in v1.130.0+.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using System.Collections.Generic;
using System.Text.Json;
using Pulumi;
using AliCloud = Pulumi.AliCloud;

class MyStack : Stack
{
    public MyStack()
    {
        var config = new Config();
        var configMapName = config.Get("configMapName") ?? "examplename";
        var exampleNamespace = new AliCloud.Sae.Namespace("exampleNamespace", new AliCloud.Sae.NamespaceArgs
        {
            NamespaceId = "cn-hangzhou:yourname",
            NamespaceName = "example_value",
            NamespaceDescription = "your_description",
        });
        var exampleConfigMap = new AliCloud.Sae.ConfigMap("exampleConfigMap", new AliCloud.Sae.ConfigMapArgs
        {
            Data = JsonSerializer.Serialize(new Dictionary<string, object?>
            {
                { "env.home", "/root" },
                { "env.shell", "/bin/sh" },
            }),
            NamespaceId = exampleNamespace.NamespaceId,
        });
        var nameRegex = exampleNamespace.NamespaceId.Apply(namespaceId => AliCloud.Sae.GetConfigMaps.InvokeAsync(new AliCloud.Sae.GetConfigMapsArgs
        {
            NamespaceId = namespaceId,
            NameRegex = "^example",
        }));
        this.SaeConfigMapId = nameRegex.Apply(nameRegex => nameRegex.Maps[0].Id);
    }

    [Output("saeConfigMapId")]
    public Output<string> SaeConfigMapId { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"encoding/json"

	"github.com/pulumi/pulumi-alicloud/sdk/v3/go/alicloud/sae"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi/config"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		cfg := config.New(ctx, "")
		configMapName := "examplename"
		if param := cfg.Get("configMapName"); param != "" {
			configMapName = param
		}
		exampleNamespace, err := sae.NewNamespace(ctx, "exampleNamespace", &sae.NamespaceArgs{
			NamespaceId:          pulumi.String("cn-hangzhou:yourname"),
			NamespaceName:        pulumi.String("example_value"),
			NamespaceDescription: pulumi.String("your_description"),
		})
		if err != nil {
			return err
		}
		tmpJSON0, err := json.Marshal(map[string]interface{}{
			"env.home":  "/root",
			"env.shell": "/bin/sh",
		})
		if err != nil {
			return err
		}
		json0 := string(tmpJSON0)
		_, err = sae.NewConfigMap(ctx, "exampleConfigMap", &sae.ConfigMapArgs{
			Data:        pulumi.String(json0),
			NamespaceId: exampleNamespace.NamespaceId,
		})
		if err != nil {
			return err
		}
		ctx.Export("saeConfigMapId", nameRegex.ApplyT(func(nameRegex sae.GetConfigMapsResult) (string, error) {
			return nameRegex.Maps[0].Id, nil
		}).(pulumi.StringOutput))
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import json
import pulumi_alicloud as alicloud

config = pulumi.Config()
config_map_name = config.get("configMapName")
if config_map_name is None:
    config_map_name = "examplename"
example_namespace = alicloud.sae.Namespace("exampleNamespace",
    namespace_id="cn-hangzhou:yourname",
    namespace_name="example_value",
    namespace_description="your_description")
example_config_map = alicloud.sae.ConfigMap("exampleConfigMap",
    data=json.dumps({
        "env.home": "/root",
        "env.shell": "/bin/sh",
    }),
    namespace_id=example_namespace.namespace_id)
name_regex = example_namespace.namespace_id.apply(lambda namespace_id: alicloud.sae.get_config_maps(namespace_id=namespace_id,
    name_regex="^example"))
pulumi.export("saeConfigMapId", name_regex.maps[0].id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as alicloud from "@pulumi/alicloud";

const config = new pulumi.Config();
const configMapName = config.get("configMapName") || "examplename";
const exampleNamespace = new alicloud.sae.Namespace("exampleNamespace", {
    namespaceId: "cn-hangzhou:yourname",
    namespaceName: "example_value",
    namespaceDescription: "your_description",
});
const exampleConfigMap = new alicloud.sae.ConfigMap("exampleConfigMap", {
    data: JSON.stringify({
        "env.home": "/root",
        "env.shell": "/bin/sh",
    }),
    namespaceId: exampleNamespace.namespaceId,
});
const nameRegex = exampleNamespace.namespaceId.apply(namespaceId => alicloud.sae.getConfigMaps({
    namespaceId: namespaceId,
    nameRegex: "^example",
}));
export const saeConfigMapId = nameRegex.maps[0].id;
```


{{< /example >}}





{{% /examples %}}




## Using getConfigMaps {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getConfigMaps<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetConfigMapsArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetConfigMapsResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_config_maps(</span><span class="nx">ids</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">,</span>
                    <span class="nx">name_regex</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                    <span class="nx">namespace_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                    <span class="nx">output_file</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                    <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetConfigMapsResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetConfigMaps<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetConfigMapsArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetConfigMapsResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetConfigMaps` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetConfigMaps </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetConfigMapsResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetConfigMapsArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="namespaceid_csharp">
<a href="#namespaceid_csharp" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The NamespaceId of Config Maps.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of Config Map IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_csharp">
<a href="#nameregex_csharp" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by Config Map name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_csharp">
<a href="#outputfile_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="namespaceid_go">
<a href="#namespaceid_go" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The NamespaceId of Config Maps.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Config Map IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_go">
<a href="#nameregex_go" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by Config Map name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_go">
<a href="#outputfile_go" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="namespaceid_nodejs">
<a href="#namespaceid_nodejs" style="color: inherit; text-decoration: inherit;">namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The NamespaceId of Config Maps.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of Config Map IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_nodejs">
<a href="#nameregex_nodejs" style="color: inherit; text-decoration: inherit;">name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by Config Map name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_nodejs">
<a href="#outputfile_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="namespace_id_python">
<a href="#namespace_id_python" style="color: inherit; text-decoration: inherit;">namespace_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The NamespaceId of Config Maps.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of Config Map IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_regex_python">
<a href="#name_regex_python" style="color: inherit; text-decoration: inherit;">name_<wbr>regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by Config Map name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="output_file_python">
<a href="#output_file_python" style="color: inherit; text-decoration: inherit;">output_<wbr>file</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## getConfigMaps Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maps_csharp">
<a href="#maps_csharp" style="color: inherit; text-decoration: inherit;">Maps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getconfigmapsmap">List&lt;Pulumi.<wbr>Ali<wbr>Cloud.<wbr>Sae.<wbr>Outputs.<wbr>Get<wbr>Config<wbr>Maps<wbr>Map&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_csharp">
<a href="#names_csharp" style="color: inherit; text-decoration: inherit;">Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespaceid_csharp">
<a href="#namespaceid_csharp" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_csharp">
<a href="#nameregex_csharp" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_csharp">
<a href="#outputfile_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maps_go">
<a href="#maps_go" style="color: inherit; text-decoration: inherit;">Maps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getconfigmapsmap">[]Get<wbr>Config<wbr>Maps<wbr>Map</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_go">
<a href="#names_go" style="color: inherit; text-decoration: inherit;">Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespaceid_go">
<a href="#namespaceid_go" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_go">
<a href="#nameregex_go" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_go">
<a href="#outputfile_go" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maps_nodejs">
<a href="#maps_nodejs" style="color: inherit; text-decoration: inherit;">maps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getconfigmapsmap">Get<wbr>Config<wbr>Maps<wbr>Map[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_nodejs">
<a href="#names_nodejs" style="color: inherit; text-decoration: inherit;">names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespaceid_nodejs">
<a href="#namespaceid_nodejs" style="color: inherit; text-decoration: inherit;">namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_nodejs">
<a href="#nameregex_nodejs" style="color: inherit; text-decoration: inherit;">name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_nodejs">
<a href="#outputfile_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maps_python">
<a href="#maps_python" style="color: inherit; text-decoration: inherit;">maps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getconfigmapsmap">Sequence[Get<wbr>Config<wbr>Maps<wbr>Map]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_python">
<a href="#names_python" style="color: inherit; text-decoration: inherit;">names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespace_id_python">
<a href="#namespace_id_python" style="color: inherit; text-decoration: inherit;">namespace_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_regex_python">
<a href="#name_regex_python" style="color: inherit; text-decoration: inherit;">name_<wbr>regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="output_file_python">
<a href="#output_file_python" style="color: inherit; text-decoration: inherit;">output_<wbr>file</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getconfigmapsmap">Get<wbr>Config<wbr>Maps<wbr>Map</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="configmapid_csharp">
<a href="#configmapid_csharp" style="color: inherit; text-decoration: inherit;">Config<wbr>Map<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The first ID of the resource.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="createtime_csharp">
<a href="#createtime_csharp" style="color: inherit; text-decoration: inherit;">Create<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Creation Time of the ConfigMap.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="data_csharp">
<a href="#data_csharp" style="color: inherit; text-decoration: inherit;">Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ConfigMap instance data. The value's format is a `json` string
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_csharp">
<a href="#description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Description of Config Map.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Config Map.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ConfigMap instance name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespaceid_csharp">
<a href="#namespaceid_csharp" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The NamespaceId of Config Maps.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="configmapid_go">
<a href="#configmapid_go" style="color: inherit; text-decoration: inherit;">Config<wbr>Map<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The first ID of the resource.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="createtime_go">
<a href="#createtime_go" style="color: inherit; text-decoration: inherit;">Create<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Creation Time of the ConfigMap.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="data_go">
<a href="#data_go" style="color: inherit; text-decoration: inherit;">Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ConfigMap instance data. The value's format is a `json` string
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_go">
<a href="#description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Description of Config Map.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Config Map.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ConfigMap instance name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespaceid_go">
<a href="#namespaceid_go" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The NamespaceId of Config Maps.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="configmapid_nodejs">
<a href="#configmapid_nodejs" style="color: inherit; text-decoration: inherit;">config<wbr>Map<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The first ID of the resource.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="createtime_nodejs">
<a href="#createtime_nodejs" style="color: inherit; text-decoration: inherit;">create<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Creation Time of the ConfigMap.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="data_nodejs">
<a href="#data_nodejs" style="color: inherit; text-decoration: inherit;">data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ConfigMap instance data. The value's format is a `json` string
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_nodejs">
<a href="#description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Description of Config Map.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Config Map.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ConfigMap instance name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespaceid_nodejs">
<a href="#namespaceid_nodejs" style="color: inherit; text-decoration: inherit;">namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The NamespaceId of Config Maps.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="config_map_id_python">
<a href="#config_map_id_python" style="color: inherit; text-decoration: inherit;">config_<wbr>map_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The first ID of the resource.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="create_time_python">
<a href="#create_time_python" style="color: inherit; text-decoration: inherit;">create_<wbr>time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Creation Time of the ConfigMap.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="data_python">
<a href="#data_python" style="color: inherit; text-decoration: inherit;">data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ConfigMap instance data. The value's format is a `json` string
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_python">
<a href="#description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Description of Config Map.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Config Map.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ConfigMap instance name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespace_id_python">
<a href="#namespace_id_python" style="color: inherit; text-decoration: inherit;">namespace_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The NamespaceId of Config Maps.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-alicloud">https://github.com/pulumi/pulumi-alicloud</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`alicloud` Terraform Provider](https://github.com/aliyun/terraform-provider-alicloud).{{% /md %}}</dd>
</dl>

