---
title: Developing sample code
description: 15
---

&#9;

<p><strong>1. In the MainActivity.kt file, locate following line to create an Image Super-Resolution analyzer.</strong></p>
<pre><div id="copy-button6" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>// TODO Create an Image Super-Resolution instance.</code></pre>

<p><strong>2. Initialize the ML Kit Image Super-Resolution service.</strong></p>
<pre><div id="copy-button7" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>private val analyzer by lazy {
&#9;MLImageSuperResolutionAnalyzerFactory.getInstance()
&#9;&#9;.imageSuperResolutionAnalyzer
}</code></pre>

<aside class="special">
  <p><strong>Note:</strong> You can use custom parameter settings. You can see the code sample below.</p>
<pre><div id="copy-button8" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>val settings= MLImageSuperResolutionAnalyzerSetting.Factory()
&#9;.setScale(MLImageSuperResolutionAnalyzerSetting.ISR_SCALE_1X)
&#9;.create()
analyzer= MLImageSuperResolutionAnalyzerFactory.getInstance()
&#9;.getImageSuperResolutionAnalyzer(settings)</code></pre>
  <p>You can initialize analyzer in both way. In this codelab, basic initialization will be used.</p>
</aside>
