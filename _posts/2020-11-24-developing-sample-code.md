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
<pre><div id="copy-button10" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>...
presenter.startGetImageProcess()</code></pre>

<p><strong>5. Go to MainPresenter, locate the following line for trigger the gallery process.</strong></p>
<pre><div id="copy-button11" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>// TODO Set result code for gallery intent and trigger the process.</code></pre>

<p><strong>6. Add the following code in MainPresenter to set the request code for gallery intent and trigger the process.</strong></p>
<pre><div id="copy-button12" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>view?.getImage(GALLERY_REQ_CODE)</code></pre>

<p><strong>7. After triggering go to MainActivity and locate the following line to create and start gallery intent.</strong></p>
<pre><div id="copy-button13" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>// TODO Create and start gallery intent.</code></pre>

<p><strong>8. Add following code in MainActivity for creating and starting intent.</strong></p>
<pre><div id="copy-button14" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>val galleryIntent = Intent(Intent.ACTION_PICK, MediaStore.Images.Media.EXTERNAL_CONTENT_URI)
galleryIntent.type = "image/*"
val mimeTypes = arrayOf("image/jpeg", "image/png", "image/jpg")
galleryIntent.putExtra(Intent.EXTRA_MIME_TYPES, mimeTypes)
galleryIntent.flags = Intent.FLAG_GRANT_READ_URI_PERMISSION

startActivityForResult(galleryIntent, code)</code></pre>

<p><strong>9. Locate the following code in MainActivity. We will catch the gallery result in MainActivity file. After catching we will send the result to presenter for analyze.</strong></p>
<pre><div id="copy-button15" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>// TODO Get the result and sent to presenter for analyze.</code></pre>

<p><strong>10. Add following code for analyze the result.</strong></p>
<pre><div id="copy-button16" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>presenter.onActivityResult(requestCode, resultCode, data)</code></pre>

<p><strong>11. Go to MainPresenter again. After activity result get uri from selected image. Locate the following code.</strong></p>
<pre><div id="copy-button17" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>// TODO Get uri from the result if the process successfully done.</code></pre>

<p><strong>12. Add following codes in MainPresenter located area.</strong></p>
<pre><div id="copy-button17" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>when (requestCode) {
    GALLERY_REQ_CODE -> {
        if (resultCode == Activity.RESULT_OK) {
            data?.data?.let { uri ->
                // After getting uri from data we are sending uri to view.
                view?.createBitmapAndStartResolution(uri)
            }
        }
    }
}</code></pre>






