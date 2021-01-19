<h2><strong>Creating a Project</strong></h2>
<p><strong>Step 1</strong>: Start Android Studio.</p>
<p><strong>Step 2</strong>: Choose <strong>File</strong> &gt; <strong>Open</strong>, go to the directory where the sample project is decompressed, and click <strong>OK</strong>.<br><img style="width: 376.00px" src="https://github.com/iebayirli/ImageSuperResolutionCodelab/blob/master/assets/folderStructure.PNG" onclick="imageclick(src)"></p>

<p><strong>Step 3</strong>: Configure the AppGallery Connect plug-in, Maven repository address, build dependencies, obfuscation scripts, and permissions. (These items have been configured in the sample code. If any of them does not meet your requirements, change it in your own project.)</p>
<p><strong>1. Configure the Maven repository address and AppGallery Connect plug-in in the project's build.gradle file.</strong></p>

• Go to <strong>allprojects</strong> &gt; <strong>repositories</strong> and configure the Maven repository address for the HMS Core SDK.
<pre><div id="copy-button1" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>allprojects {
&#9;repositories {
&#9;&#9;...
&#9;&#9;maven { url 'https://developer.huawei.com/repo/' }
&#9;&#9;...
&#9;}
}</code>
</pre>

• Go to <strong>buildscript </strong> &gt; <strong>repositories</strong> and configure the Maven repository address for the HMS Core SDK.
<pre><div id="copy-button2" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div>
<code>buildscript {
&#9;repositories {
&#9;&#9;maven {url 'https://developer.huawei.com/repo/'}
&#9;&#9;...
&#9;}
&#9;...
} </code></pre>

• Go to <strong>buildscript </strong> &gt; <strong>dependencies </strong> and make sure AGC plugin dependency has been configured.
<pre><div id="copy-button3" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div>
<code>buildscript{
&#9;dependencies {
&#9;&#9;classpath 'com.huawei.agconnect:agcp:1.4.0.300'
&#9;}
}</code></pre>

<p><strong>2. Review and configure the dependency package in the app’s build.gradle file.</strong></p>

•	Make sure the Image Super-Resolution dependency has been added. If it’s not added add it as following the <strong>dependencies</strong> section in the <strong>build.gradle</strong> file.

<pre><div id="copy-button4" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div>
<code>dependencies {
&#9;...
&#9;implementation "com.huawei.hms:ml-computer-vision-imageSuperResolution:2.0.2.300"
}</code></pre>

•	Configure targetSdkVersion

<pre><div id="copy-button5" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div>
<code>android {
&#9;...
&#9;defaultConfig {
&#9;&#9;...
&#9;&#9;targetSdkVersion 28
&#9;&#9;...
&#9;}
&#9;...
}</code></pre>

<aside class="special">
  <p><strong>Note:</strong> When using the image super-resolution service, you need to set the value of <strong>targetSdkVersion</strong> less than 29 in the <strong>build.gradle</strong> file.</p>
</aside>

<aside class="special">
  <p><strong>Note:</strong> Make sure that you configure apply plugin: ‘com.huawei.agconnect' after apply plugin:‘com.android.application'.</p>
</aside>

<p><strong>Step 4</strong>: In the Android Studio window, choose <strong>File &gt; Sync Project</strong> with Gradle File to synchronize the project.</p>
<p><strong>Step 5</strong>: Find and open the <strong>MainActivity.kt</strong> and <strong>MainPresenter.kt</strong> files. The basic code snippets in these files will be completed during the implementation process.</p>
