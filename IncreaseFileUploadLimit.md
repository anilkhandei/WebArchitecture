<h1 id="increase-asp.net-app-file-upload-max-limit">Increase <a href="http://ASP.Net">ASP.Net</a> App File Upload Max Limit</h1>
<p>In the Web App Web.Config file change the</p>
<pre class=" language-xml"><code class="prism  language-xml"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>httpRuntime</span> <span class="token attr-name">targetFramework</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>4.5<span class="token punctuation">"</span></span> <span class="token attr-name">executionTimeout</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>360<span class="token punctuation">"</span></span> <span class="token attr-name">requestValidationMode</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>2.0<span class="token punctuation">"</span></span> <span class="token attr-name">maxRequestLength</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>5123<span class="token punctuation">"</span></span> <span class="token punctuation">/&gt;</span></span>
</code></pre>
<blockquote>
<p>Change maxRequestLength from 5123 to anything you want in bytes</p>
</blockquote>
<blockquote>
<p>Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>

