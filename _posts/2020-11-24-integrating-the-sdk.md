<h2><strong>Creating a Project</strong></h2>
<p><strong>Step 1</strong>: Start Android Studio.</p>
<p><strong>Step 2</strong>: Choose <strong>File</strong> &gt; <strong>Open</strong>, go to the directory where the sample project is decompressed, and click <strong>OK</strong>.<br><img style="width: 376.00px" src="https://github.com/iebayirli/ImageSuperResolutionCodelab/blob/master/assets/folderStructure.png" onclick="imageclick(src)"></p>
<p><strong>Step 3</strong>: Configure the AppGallery Connect plug-in, Maven repository address, build dependencies, obfuscation scripts, and permissions. (These items have been configured in the sample code. If any of them does not meet your requirements, change it in your own project.)</p>
<p><strong>1. Configure the Maven repository address and AppGallery Connect plug-in in the project's build.gradle file.</strong></p>
<ul>
	<li>Go to <strong>allprojects</strong> &gt; <strong>repositories</strong> and configure the Maven repository address for the HMS Core SDK.<pre><div id="copy-button1" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code><span class="pln">allprojects </span><span class="pun">{</span><span class="pln">
		repositories </span><span class="pun">{</span><span class="pln">
			maven </span><span class="pun">{</span><span class="pln"> url </span><span class="str">'https://developer.huawei.com/repo/'</span><span class="pln"> </span><span class="pun">}</span><span class="pln">
			</span><span class="pun">...</span><span class="pln">
		</span><span class="pun">}</span><span class="pln">
	</span><span class="pun">}</span><span class="pln">
	</span></code></pre>
	</li>
	<li>Go to <strong>buildscript</strong> &gt; <strong>repositories</strong> and configure the Maven repository address for the HMS Core SDK.<pre><div id="copy-button2" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code><span class="pln">buildscript </span><span class="pun">{</span><span class="pln">
		repositories </span><span class="pun">{</span><span class="pln">
		   maven </span><span class="pun">{</span><span class="pln">url </span><span class="str">'https://developer.huawei.com/repo/'</span><span class="pun">}</span><span class="pln">
			</span><span class="pun">...</span><span class="pln">
		</span><span class="pun">}</span><span class="pln">
		</span><span class="pun">...</span><span class="pln">
	</span><span class="pun">}</span><span class="pln">
	</span></code></pre>
	</li>
	<li>Go to <strong>buildscript</strong> &gt; <strong>dependencies</strong> and add build dependencies.<pre><div id="copy-button3" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code><span class="pln">buildscript </span><span class="pun">{</span><span class="pln">
		dependencies </span><span class="pun">{</span><span class="pln">
     </span><span class="str">                   //Replace {agconnect_version} with the actual AGC plugin version number.</span><span class="pln">
     </span><span class="str">                   //Example: classpath 'com.huawei.agconnect:agcp: 1.4.1.300'</span><span class="pln">
			classpath </span><span class="str">'com.huawei.agconnect:agcp:{agconnect_version}'</span><span class="pln">
		</span><span class="pun">}</span><span class="pln">
	</span><span class="pun">}</span><span class="pln">
	</span></code></pre>
	</li>
</ul>
<p><strong>2. Configure the dependency package in the app's build.gradle file.</strong></p>
<ul>
	<li>Make sure the Image Super-Resolution dependency has been added. If it’s not added add it as following the <strong>dependencies</strong> section in the <strong>build.gradle</strong> file.<pre><div id="copy-button4" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code><span class="pln">dependencies </span><span class="pun">{</span><span class="pln">
		</span><span class="pun">...</span><span class="pln">
    </span><span class="str">            //Image Super-Resolution</span><span class="pln">
		implementation </span><span class="str">'com.huawei.hms:ml-computer-vision-imageSuperResolution:2.0.2.300'</span><span class="pln">
		</span><span class="pun">...</span><span class="pln">
	</span><span class="pun">}</span><span class="pln">
	</span></code></pre>
	</li>
	<li>Configure targetSdkVersion
	<pre><div id="copy-button5" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>
  <span class="pln">android</span><span class="pun">{</span>
  <span class="pln">       defaultConfig </span><span class="pun">{</span>
  <span class="pun"></span><span class="pln">		 ...</span>
  <span class="pln"></span><span class="str">	  	 targetSdkVersion 28</span>
  <span class="pln"></span><span class="pln">		 ...</span>
  <span class="pln"></span><span class="pun">      }</span>
  <span class="pln"></span><span class="pun">}</span>
  <span class="pln"></span></code></pre>
	</li>
	<li>Add the following information under <strong>apply plugin: 'com.android.application'</strong> in the file header:<pre><div id="copy-button6" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code><span class="pln">apply plugin</span><span class="pun">:</span><span class="pln"> </span><span class="str">'com.huawei.agconnect'</span><span class="pln">
	</span></code></pre>
	</li>
<aside class="special">
    <p><strong>Note:</strong> When using the image super-resolution service, you need to set the value of <strong>targetSdkVersion</strong> less than 29 in the <strong>build.gradle</strong> file.</p>
</aside>
<aside class="special">
   <p><strong>Note:</strong> Make sure that you configure apply plugin: ‘com.huawei.agconnect' after apply plugin:‘com.android.application'.</p>
</aside>
</ul>
<p><strong>Step 4</strong>: In the Android Studio window, choose <strong>File > Sync Project</strong> with Gradle File to synchronize the project.</p>
<p><strong>Step 5</strong>: Find and open the <strong>MainActivity.kt</strong> and <strong>MainPresenter.kt</strong> files. The basic code snippets in these files will be completed during the implementation process.
</p>
<p>
<pre>
<div id="copy-button4" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div>
 <span class="pun">
  <pre>
    selamlar ismail emr
bayirli
  </pre>
</span>
</pre>
</p>


