
---
title: "getSequences"
title_tag: "snowflake.getSequences"
meta_desc: "Documentation for the snowflake.getSequences function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->



{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Snowflake = Pulumi.Snowflake;

class MyStack : Stack
{
    public MyStack()
    {
        var current = Output.Create(Snowflake.GetSequences.InvokeAsync(new Snowflake.GetSequencesArgs
        {
            Database = "MYDB",
            Schema = "MYSCHEMA",
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-snowflake/sdk/go/snowflake"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := snowflake.GetSequences(ctx, &GetSequencesArgs{
			Database: "MYDB",
			Schema:   "MYSCHEMA",
		}, nil)
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
import pulumi_snowflake as snowflake

current = snowflake.get_sequences(database="MYDB",
    schema="MYSCHEMA")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as snowflake from "@pulumi/snowflake";

const current = pulumi.output(snowflake.getSequences({
    database: "MYDB",
    schema: "MYSCHEMA",
}));
```


{{< /example >}}





{{% /examples %}}




## Using getSequences {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getSequences<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetSequencesArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetSequencesResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_sequences(</span><span class="nx">database</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                  <span class="nx">schema</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                  <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetSequencesResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSequences<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetSequencesArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetSequencesResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetSequences` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetSequences </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetSequencesResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetSequencesArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="database_csharp">
<a href="#database_csharp" style="color: inherit; text-decoration: inherit;">Database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="schema_csharp">
<a href="#schema_csharp" style="color: inherit; text-decoration: inherit;">Schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="database_go">
<a href="#database_go" style="color: inherit; text-decoration: inherit;">Database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="schema_go">
<a href="#schema_go" style="color: inherit; text-decoration: inherit;">Schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="database_nodejs">
<a href="#database_nodejs" style="color: inherit; text-decoration: inherit;">database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="schema_nodejs">
<a href="#schema_nodejs" style="color: inherit; text-decoration: inherit;">schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="database_python">
<a href="#database_python" style="color: inherit; text-decoration: inherit;">database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="schema_python">
<a href="#schema_python" style="color: inherit; text-decoration: inherit;">schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getSequences Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="database_csharp">
<a href="#database_csharp" style="color: inherit; text-decoration: inherit;">Database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
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
        <span id="schema_csharp">
<a href="#schema_csharp" style="color: inherit; text-decoration: inherit;">Schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sequences_csharp">
<a href="#sequences_csharp" style="color: inherit; text-decoration: inherit;">Sequences</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsequencessequence">List&lt;Get<wbr>Sequences<wbr>Sequence&gt;</a></span>
    </dt>
    <dd>{{% md %}}The sequences in the schema
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="database_go">
<a href="#database_go" style="color: inherit; text-decoration: inherit;">Database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
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
        <span id="schema_go">
<a href="#schema_go" style="color: inherit; text-decoration: inherit;">Schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sequences_go">
<a href="#sequences_go" style="color: inherit; text-decoration: inherit;">Sequences</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsequencessequence">[]Get<wbr>Sequences<wbr>Sequence</a></span>
    </dt>
    <dd>{{% md %}}The sequences in the schema
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="database_nodejs">
<a href="#database_nodejs" style="color: inherit; text-decoration: inherit;">database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
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
        <span id="schema_nodejs">
<a href="#schema_nodejs" style="color: inherit; text-decoration: inherit;">schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sequences_nodejs">
<a href="#sequences_nodejs" style="color: inherit; text-decoration: inherit;">sequences</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsequencessequence">Get<wbr>Sequences<wbr>Sequence[]</a></span>
    </dt>
    <dd>{{% md %}}The sequences in the schema
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="database_python">
<a href="#database_python" style="color: inherit; text-decoration: inherit;">database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
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
        <span id="schema_python">
<a href="#schema_python" style="color: inherit; text-decoration: inherit;">schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sequences_python">
<a href="#sequences_python" style="color: inherit; text-decoration: inherit;">sequences</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsequencessequence">Sequence[Get<wbr>Sequences<wbr>Sequence]</a></span>
    </dt>
    <dd>{{% md %}}The sequences in the schema
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getsequencessequence">Get<wbr>Sequences<wbr>Sequence</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="comment_csharp">
<a href="#comment_csharp" style="color: inherit; text-decoration: inherit;">Comment</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="database_csharp">
<a href="#database_csharp" style="color: inherit; text-decoration: inherit;">Database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="schema_csharp">
<a href="#schema_csharp" style="color: inherit; text-decoration: inherit;">Schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="comment_go">
<a href="#comment_go" style="color: inherit; text-decoration: inherit;">Comment</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="database_go">
<a href="#database_go" style="color: inherit; text-decoration: inherit;">Database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="schema_go">
<a href="#schema_go" style="color: inherit; text-decoration: inherit;">Schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="comment_nodejs">
<a href="#comment_nodejs" style="color: inherit; text-decoration: inherit;">comment</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="database_nodejs">
<a href="#database_nodejs" style="color: inherit; text-decoration: inherit;">database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="schema_nodejs">
<a href="#schema_nodejs" style="color: inherit; text-decoration: inherit;">schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="comment_python">
<a href="#comment_python" style="color: inherit; text-decoration: inherit;">comment</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="database_python">
<a href="#database_python" style="color: inherit; text-decoration: inherit;">database</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The database from which to return the schemas from.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="schema_python">
<a href="#schema_python" style="color: inherit; text-decoration: inherit;">schema</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The schema from which to return the sequences from.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-snowflake">https://github.com/pulumi/pulumi-snowflake</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`snowflake` Terraform Provider](https://github.com/chanzuckerberg/terraform-provider-snowflake).{{% /md %}}</dd>
</dl>

