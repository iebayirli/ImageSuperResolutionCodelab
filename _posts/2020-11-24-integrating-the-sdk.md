<h2><strong>Creating a Project</strong></h2>
<p><strong>Step 1</strong>: Start Android Studio.</p>
<p><strong>Step 2</strong>: Choose <strong>File</strong> &gt; <strong>Open</strong>, go to the directory where the sample project is decompressed, and click <strong>OK</strong>.<br><img style="width: 376.00px" src="https://github.com/iebayirli/ImageSuperResolutionCodelab/blob/master/assets/folderStructure.png" onclick="imageclick(src)"></p>

<p><strong>Step 3</strong>: Configure the AppGallery Connect plug-in, Maven repository address, build dependencies, obfuscation scripts, and permissions. (These items have been configured in the sample code. If any of them does not meet your requirements, change it in your own project.)</p>
<p><strong>1. Configure the Maven repository address and AppGallery Connect plug-in in the project's build.gradle file.</strong></p>

• Go to <strong>allprojects</strong> &gt; <strong>repositories</strong> and configure the Maven repository address for the HMS Core SDK.
<pre><div id="copy-button1" class="copy-btn" title="Copy" onclick="copyCode(this.id)"> </div>
<code>
allprojects {
&#9;repositories {
&#9;&#9;...
&#9;&#9;maven { url 'https://developer.huawei.com/repo/' }
&#9;&#9;...
&#9;}
}
</code>
</pre>

• Go to <strong>buildscript </strong> &gt; <strong>repositories</strong> and configure the Maven repository address for the HMS Core SDK.</li>
<pre><div id="copy-button2" class="copy-btn" title="Copy" onclick="copyCode(this.id)"> 
<code>
buildscript {
&#9;repositories {
&#9;&#9;maven {url 'https://developer.huawei.com/repo/'}
&#9;&#9;...
&#9;}
&#9;...
}
 </div> </code></pre>

  
