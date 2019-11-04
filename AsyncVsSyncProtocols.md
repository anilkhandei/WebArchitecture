<h1 id="synchronous-and-asynchronous-protocols">Synchronous and Asynchronous protocols</h1>
<blockquote>
<p>HTTP/HTTP(S):  Synchronous<br>
AMQP: Asynchronous</p>
</blockquote>
<p>While working with HTTP or HTTP(s) protocols for communication, we need to keep in mind that, HTTP is a synchronous protocol.</p>
<p>However the underlying client side code may be-</p>
<ol>
<li>Synchronous<br>
It means that the thread is blocked until the HTTP response is returned.</li>
<li>Asynchronous<br>
It means that the thread is not blocked but the HTTP response will ultimately reach a call back.</li>
</ol>
<p>In both the above scenarios the client is dependent on the response and can only continue its task when the response is received.</p>
<blockquote>
<p>AMQP (Advanced Message Queuing Protocol)</p>
</blockquote>
<p>In case of Asynchronous communication protocol, the client does not depend on a response, just sends the request and continues its task. For example sending messages to the MSMQ or RabbitMQ.</p>
<blockquote>
<p>Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>

