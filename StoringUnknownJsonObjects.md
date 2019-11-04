<h1 id="how-to-store-an-unknown-json--object-in-mvc-model-asp.net-core">How to store an unknown JSON  object in MVC Model (<a href="http://ASP.NET">ASP.NET</a> Core)</h1>
<h1 id="problem">Problem:</h1>
<p>Many times while working with JSON data we come across scenarios where the data is unknown and need to be stored as it is. We cannot create a predefined model to map the unknown data. So we need to find a way how we can map the unknown JSON objects to our properties in Model.</p>
<h2 id="solution">Solution</h2>
<p>Since we cannot create a complex type for an unknown data. We need to use a type that can store the json object as it is.<br>
Can we map to a string Type property?<br>
Answer is No it doesn’t work. When we try to map a JSON object to string type dotnet maps null value.</p>
<p>There are 2 ways in which we can map unknown JSON objects to model properties-</p>
<ul>
<li>JToken</li>
<li>object</li>
</ul>
<h3 id="jtoken">JToken</h3>
<p>If you are using NewtonSoft.JSON then you can use JToken type to map unknown data to model property.<br>
Example model using <strong>JToken</strong> type-</p>
<pre><code>public class ComplexDataModel
{
    public int Id { get; set; }
    public int UserId { get; set; }
    public JToken Payload { get; set; }
    public int ContextTypeId { get; set; }
    public int SessionId { get; set; }
    public int EventTypeId { get; set; }
}
</code></pre>
<p>Like so-<br>
<code>public JToken Payload { get; set; }</code></p>
<h3 id="object">object</h3>
<p>The easiest way is to use object type when you don’t want to use a 3rd party library like <a href="http://Json.net">Json.net</a></p>
<p>Example model using <strong>object</strong> type-</p>
<pre><code>public class ComplexDataModel
{
    public int Id { get; set; }
    public int UserId { get; set; }
    public object Payload { get; set; }
    public int ContextTypeId { get; set; }
    public int SessionId { get; set; }
    public int EventTypeId { get; set; }
}
</code></pre>
<p>Like so-<br>
<code>public object Payload { get; set; }</code></p>

