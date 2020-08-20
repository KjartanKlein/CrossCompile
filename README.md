# CrossCompile
Rust cross copile stup from x86 to arm


<p>To do this follow these steps carefully.</p>
<ol type="1">
<li>Open your terminal (or WSL)</li>
<li>
<p>Install the ARM linker and other useful tools</p>
<p><code>apt install subversion</code></p>
<p><code>sudo svn checkout https://github.com/raspberrypi/tools/trunk/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf /usr/local/share/raspi-tools</code></p>
<p><code>sudo ln -s /usr/local/share/raspi-tools/bin/arm-linux-gnueabihf-* /usr/local/bin</code></p>
</li>
<li>
<p>open up the directory at ~/.cargo</p>
<p><code>cd ~/.cargo</code></p>
</li>
<li>
<p>make sure that the config file exists</p>
<p><code>touch config</code></p>
</li>
<li>
<p>open the config file</p>
<p><code>nano config</code></p>
</li>
<li>
<p>add the following text [build] target = &ldquo;arm-unknown-linux-gnueabihf&rdquo;</p>
<pre><code>[target.arm-unknown-linux-gnueabihf]
linker = "arm-linux-gnueabihf-gcc"</code></pre>
</li>
<li>
<p>add the target to rustup</p>
<p><code>rustup target add arm-unknown-linux-gnueabihf</code></p>
</li>
<li>
<p>Add the /usr/local/bin path to your PATH variable.&nbsp; This is where your shell (in the terminal) looks for programs. Usually this looks something like this in your ~/.bashrc.&nbsp; If not, add it! export PATH="/usr/local/bin:$PATH"</p>
</li>
</ol>
