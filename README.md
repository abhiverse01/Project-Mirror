
<body>

<h1>Project-Mirro</h1>

<p>This guide will help you mirror your mobile phone screen on your desktop using ADB (Android Debug Bridge) and <code>scrcpy</code>. Follow the steps below to set up and run the tools.</p>

<h2>Requirements</h2>
<ul>
    <li>Android device with Developer Options enabled.</li>
    <li>USB cable to connect your phone to your desktop.</li>
    <li>A computer running Windows with ADB and <code>scrcpy</code> installed.</li>
</ul>

<h2>Steps</h2>

<h3>Mobile Setup</h3>
<ol>
    <li>
        <strong>Enable Developer Options</strong>:
        <ul>
            <li>On your Android device, go to <strong>Settings</strong> > <strong>About phone</strong>.</li>
            <li>Tap <strong>Build number</strong> seven times to enable Developer Options.</li>
            <li>Go back to <strong>Settings</strong> > <strong>System</strong> > <strong>Developer options</strong>.</li>
        </ul>
    </li>
    <li>
        <strong>Enable USB Debugging</strong>:
        <ul>
            <li>In Developer Options, enable <strong>USB debugging</strong>.</li>
        </ul>
    </li>
    <li>
        <strong>Enable ADB Over Network</strong> (if necessary):
        <ul>
            <li>In Developer Options, enable <strong>ADB over network</strong>.</li>
        </ul>
    </li>
</ol>

<h3>Desktop Setup</h3>
<ol>
    <li>
        <strong>Download and Extract Files</strong>:
        <ul>
            <li>Download the platform-tools package and extract it to a location on your desktop.</li>
            <li>Ensure the extracted folder contains <code>adb.exe</code> and <code>scrcpy.exe</code> along with other necessary files.</li>
        </ul>
    </li>
    <li>
        <strong>Open Terminal in Platform-Tools Folder</strong>:
        <ul>
            <li>Navigate to the platform-tools folder in File Explorer.</li>
            <li>Right-click inside the folder and select "Open in Terminal".</li>
        </ul>
    </li>
    <li>
        <strong>Connect to the Device via ADB</strong>:
        <ul>
            <li>
                <strong>Using Network</strong> (if your device is already configured for ADB over network):
                <pre><code>.\adb connect &lt;device_ip&gt;:5555</code></pre>
                Replace <code>&lt;device_ip&gt;</code> with the actual IP address of your device.
            </li>
            <li>
                <strong>Using USB</strong> (if network connection fails):
                <ol>
                    <li>Connect your phone to your desktop via USB.</li>
                    <li>Run the following command to list connected devices and ensure your device is listed:
                        <pre><code>.\adb devices</code></pre>
                    </li>
                    <li>If the device shows as <code>unauthorized</code>, authorize debugging on your phone when prompted.</li>
                    <li>Enable ADB over network:
                        <pre><code>.\adb tcpip 5555</code></pre>
                    </li>
                    <li>Disconnect the USB cable and connect using the network method as described above.</li>
                </ol>
            </li>
        </ul>
    </li>
</ol>

<h3>Running scrcpy</h3>
<ol>
    <li>
        <strong>Execute scrcpy</strong>:
        <ul>
            <li>Once ADB is connected to your device, double-click <code>scrcpy.exe</code> in the platform-tools folder.</li>
            <li>A terminal window will open. Wait for the terminal to load and initialize.</li>
        </ul>
    </li>
    <li>
        <strong>Start Mirroring</strong>:
        <ul>
            <li>Select all text in the terminal and copy it.</li>
            <li>A window displaying your phone screen should open on your desktop.</li>
        </ul>
    </li>
</ol>

<h2>Troubleshooting</h2>
<ul>
    <li>If you encounter connection issues, ensure both your desktop and mobile device are on the same network.</li>
    <li>Ensure no firewalls or network security settings are blocking the connection.</li>
    <li>Restart ADB server if necessary:
        <pre><code>.\adb kill-server
.\adb start-server</code></pre>
    </li>
</ul>

<p>By following these steps, you should be able to successfully mirror your mobile phone screen on your desktop. Enjoy using <code>scrcpy</code> for a seamless mirroring experience!</p>

</body>
</html>
