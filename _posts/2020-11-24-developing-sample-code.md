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

<p><strong>3. After initialization analyzer, locate the following line to start getting image from gallery.</strong></p>
<pre><div id="copy-button9" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>// TODO Clear view and start capturing images from gallery process.</code></pre>

<p><strong>4. Add the following code to clear UI and start gallery process.</strong></p>
<pre><div id="copy-button10" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>...presenter.startGetImageProcess()</code></pre>

<p><strong>5. Go to MainPresenter, locate the following line for trigger the gallery process.</strong></p>
<pre><div id="copy-button11" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>// TODO Set result code for gallery intent and trigger the process.</code</pre>

<p><strong>6. Add the following code in MainPresenter to set the request code for gallery intent and trigger the process.</strong></p>
<pre><div id="copy-button12" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>view?.getImage(GALLERY_REQ_CODE)</code</pre>

<p><strong>7. After triggering go to MainActivity and locate the following line to create and start gallery intent.</strong></p>
<pre><div id="copy-button13" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>// TODO Create and start gallery intent.</code</pre>


