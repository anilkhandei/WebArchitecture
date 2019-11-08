<h1 id="fileupload-to-xml-string-in-memory">FileUpload to XML string in Memory</h1>
<h2 id="requirement">Requirement:</h2>
<p>User uploads an XML file on a web application, requirement is to display the same file contents in a text area on the same screen without writing the file contents to the file system.</p>
<h2 id="solution">Solution:</h2>
<p>First convert the file contents to a byte array using stream like so.</p>
<pre class=" language-c"><code class="prism # language-c"><span class="token keyword">int</span> fileLen <span class="token operator">=</span> f_upload<span class="token punctuation">.</span>PostedFile<span class="token punctuation">.</span>ContentLength<span class="token punctuation">;</span>
byte<span class="token punctuation">[</span><span class="token punctuation">]</span> fileInBytes <span class="token operator">=</span> new byte<span class="token punctuation">[</span>f_upload<span class="token punctuation">.</span>PostedFile<span class="token punctuation">.</span>ContentLength<span class="token punctuation">]</span><span class="token punctuation">;</span>
                
<span class="token function">using</span> <span class="token punctuation">(</span>Stream s <span class="token operator">=</span> f_upload<span class="token punctuation">.</span>FileContent<span class="token punctuation">)</span>
<span class="token punctuation">{</span>
   s<span class="token punctuation">.</span><span class="token function">Read</span><span class="token punctuation">(</span>fileInBytes<span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> fileLen<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
</code></pre>
<p>Then load the byte array into the memory using memory stream like so.</p>
<pre class=" language-c"><code class="prism # language-c">XmlDocument doc <span class="token operator">=</span> new <span class="token function">XmlDocument</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token function">using</span><span class="token punctuation">(</span>MemoryStream ms<span class="token operator">=</span>new <span class="token function">MemoryStream</span><span class="token punctuation">(</span>fileInBytes<span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token punctuation">{</span>
    doc<span class="token punctuation">.</span><span class="token function">Load</span><span class="token punctuation">(</span>ms<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
fileinString <span class="token operator">=</span> doc<span class="token punctuation">.</span>InnerXml<span class="token punctuation">.</span><span class="token function">ToString</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>Now you can get the xml contents in a string and display on the text area.</p>
<blockquote>
<p>Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>

