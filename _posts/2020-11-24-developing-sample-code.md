---
title: Developing sample code
description: 15
---

&#9;

<p><strong>1. In the MainActivity.kt file, locate following line to create an Image Super-Resolution analyzer.</strong></p>
<pre><div id="copy-button1" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>// TODO Create an Image Super-Resolution instance.</code></pre>
<p><strong>2. Initialize the ML Kit Image Super-Resolution service.</strong></p>
<pre><div id="copy-button2" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>private val analyzer by lazy {
&#9;MLImageSuperResolutionAnalyzerFactory.getInstance()
&#9;&#9;.imageSuperResolutionAnalyzer
}</code></pre>
