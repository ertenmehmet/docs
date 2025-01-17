
---
title: "getAttributeDefinition"
title_tag: "google-native.healthcare/v1beta1.getAttributeDefinition"
meta_desc: "Documentation for the google-native.healthcare/v1beta1.getAttributeDefinition function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Gets the specified Attribute definition.




## Using getAttributeDefinition {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getAttributeDefinition<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetAttributeDefinitionArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetAttributeDefinitionResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_attribute_definition(</span><span class="nx">attribute_definition_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                             <span class="nx">consent_store_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                             <span class="nx">dataset_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                             <span class="nx">location</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                             <span class="nx">project</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                             <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetAttributeDefinitionResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupAttributeDefinition<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">LookupAttributeDefinitionArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupAttributeDefinitionResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupAttributeDefinition` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetAttributeDefinition </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetAttributeDefinitionResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetAttributeDefinitionArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="attributedefinitionid_csharp">
<a href="#attributedefinitionid_csharp" style="color: inherit; text-decoration: inherit;">Attribute<wbr>Definition<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="consentstoreid_csharp">
<a href="#consentstoreid_csharp" style="color: inherit; text-decoration: inherit;">Consent<wbr>Store<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="datasetid_csharp">
<a href="#datasetid_csharp" style="color: inherit; text-decoration: inherit;">Dataset<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="location_csharp">
<a href="#location_csharp" style="color: inherit; text-decoration: inherit;">Location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_csharp">
<a href="#project_csharp" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="attributedefinitionid_go">
<a href="#attributedefinitionid_go" style="color: inherit; text-decoration: inherit;">Attribute<wbr>Definition<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="consentstoreid_go">
<a href="#consentstoreid_go" style="color: inherit; text-decoration: inherit;">Consent<wbr>Store<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="datasetid_go">
<a href="#datasetid_go" style="color: inherit; text-decoration: inherit;">Dataset<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="location_go">
<a href="#location_go" style="color: inherit; text-decoration: inherit;">Location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_go">
<a href="#project_go" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="attributedefinitionid_nodejs">
<a href="#attributedefinitionid_nodejs" style="color: inherit; text-decoration: inherit;">attribute<wbr>Definition<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="consentstoreid_nodejs">
<a href="#consentstoreid_nodejs" style="color: inherit; text-decoration: inherit;">consent<wbr>Store<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="datasetid_nodejs">
<a href="#datasetid_nodejs" style="color: inherit; text-decoration: inherit;">dataset<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="location_nodejs">
<a href="#location_nodejs" style="color: inherit; text-decoration: inherit;">location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_nodejs">
<a href="#project_nodejs" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="attribute_definition_id_python">
<a href="#attribute_definition_id_python" style="color: inherit; text-decoration: inherit;">attribute_<wbr>definition_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="consent_store_id_python">
<a href="#consent_store_id_python" style="color: inherit; text-decoration: inherit;">consent_<wbr>store_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="dataset_id_python">
<a href="#dataset_id_python" style="color: inherit; text-decoration: inherit;">dataset_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="location_python">
<a href="#location_python" style="color: inherit; text-decoration: inherit;">location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_python">
<a href="#project_python" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## getAttributeDefinition Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="allowedvalues_csharp">
<a href="#allowedvalues_csharp" style="color: inherit; text-decoration: inherit;">Allowed<wbr>Values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}Possible values for the attribute. The number of allowed values must not exceed 100. An empty list is invalid. The list can only be expanded after creation.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="category_csharp">
<a href="#category_csharp" style="color: inherit; text-decoration: inherit;">Category</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The category of the attribute. The value of this field cannot be changed after creation.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="consentdefaultvalues_csharp">
<a href="#consentdefaultvalues_csharp" style="color: inherit; text-decoration: inherit;">Consent<wbr>Default<wbr>Values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}Optional. Default values of the attribute in Consents. If no default values are specified, it defaults to an empty value.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="datamappingdefaultvalue_csharp">
<a href="#datamappingdefaultvalue_csharp" style="color: inherit; text-decoration: inherit;">Data<wbr>Mapping<wbr>Default<wbr>Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Optional. Default value of the attribute in User data mappings. If no default value is specified, it defaults to an empty value. This field is only applicable to attributes of the category `RESOURCE`.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_csharp">
<a href="#description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Optional. A description of the attribute.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name of the Attribute definition, of the form `projects/{project_id}/locations/{location_id}/datasets/{dataset_id}/consentStores/{consent_store_id}/attributeDefinitions/{attribute_definition_id}`. Cannot be changed after creation.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="allowedvalues_go">
<a href="#allowedvalues_go" style="color: inherit; text-decoration: inherit;">Allowed<wbr>Values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Possible values for the attribute. The number of allowed values must not exceed 100. An empty list is invalid. The list can only be expanded after creation.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="category_go">
<a href="#category_go" style="color: inherit; text-decoration: inherit;">Category</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The category of the attribute. The value of this field cannot be changed after creation.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="consentdefaultvalues_go">
<a href="#consentdefaultvalues_go" style="color: inherit; text-decoration: inherit;">Consent<wbr>Default<wbr>Values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Optional. Default values of the attribute in Consents. If no default values are specified, it defaults to an empty value.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="datamappingdefaultvalue_go">
<a href="#datamappingdefaultvalue_go" style="color: inherit; text-decoration: inherit;">Data<wbr>Mapping<wbr>Default<wbr>Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Optional. Default value of the attribute in User data mappings. If no default value is specified, it defaults to an empty value. This field is only applicable to attributes of the category `RESOURCE`.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_go">
<a href="#description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Optional. A description of the attribute.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name of the Attribute definition, of the form `projects/{project_id}/locations/{location_id}/datasets/{dataset_id}/consentStores/{consent_store_id}/attributeDefinitions/{attribute_definition_id}`. Cannot be changed after creation.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="allowedvalues_nodejs">
<a href="#allowedvalues_nodejs" style="color: inherit; text-decoration: inherit;">allowed<wbr>Values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Possible values for the attribute. The number of allowed values must not exceed 100. An empty list is invalid. The list can only be expanded after creation.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="category_nodejs">
<a href="#category_nodejs" style="color: inherit; text-decoration: inherit;">category</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The category of the attribute. The value of this field cannot be changed after creation.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="consentdefaultvalues_nodejs">
<a href="#consentdefaultvalues_nodejs" style="color: inherit; text-decoration: inherit;">consent<wbr>Default<wbr>Values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Optional. Default values of the attribute in Consents. If no default values are specified, it defaults to an empty value.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="datamappingdefaultvalue_nodejs">
<a href="#datamappingdefaultvalue_nodejs" style="color: inherit; text-decoration: inherit;">data<wbr>Mapping<wbr>Default<wbr>Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Optional. Default value of the attribute in User data mappings. If no default value is specified, it defaults to an empty value. This field is only applicable to attributes of the category `RESOURCE`.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_nodejs">
<a href="#description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Optional. A description of the attribute.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name of the Attribute definition, of the form `projects/{project_id}/locations/{location_id}/datasets/{dataset_id}/consentStores/{consent_store_id}/attributeDefinitions/{attribute_definition_id}`. Cannot be changed after creation.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="allowed_values_python">
<a href="#allowed_values_python" style="color: inherit; text-decoration: inherit;">allowed_<wbr>values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}Possible values for the attribute. The number of allowed values must not exceed 100. An empty list is invalid. The list can only be expanded after creation.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="category_python">
<a href="#category_python" style="color: inherit; text-decoration: inherit;">category</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The category of the attribute. The value of this field cannot be changed after creation.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="consent_default_values_python">
<a href="#consent_default_values_python" style="color: inherit; text-decoration: inherit;">consent_<wbr>default_<wbr>values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}Optional. Default values of the attribute in Consents. If no default values are specified, it defaults to an empty value.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="data_mapping_default_value_python">
<a href="#data_mapping_default_value_python" style="color: inherit; text-decoration: inherit;">data_<wbr>mapping_<wbr>default_<wbr>value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Optional. Default value of the attribute in User data mappings. If no default value is specified, it defaults to an empty value. This field is only applicable to attributes of the category `RESOURCE`.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_python">
<a href="#description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Optional. A description of the attribute.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Resource name of the Attribute definition, of the form `projects/{project_id}/locations/{location_id}/datasets/{dataset_id}/consentStores/{consent_store_id}/attributeDefinitions/{attribute_definition_id}`. Cannot be changed after creation.{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-google-native">https://github.com/pulumi/pulumi-google-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>

