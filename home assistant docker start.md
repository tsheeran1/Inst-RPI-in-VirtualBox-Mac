
Run this to run the docker container for home-assistant

<pre><code>$ sudo docker run -d --name home-assistant --device /dev/ttyACM0:/dev/zwave \  
> -v /home/tom/haconfig:/config -v /etc/localtime:/etc/localtime:ro --net=host \  
homeassistant/home-assistant
</code></pre>

You need to stop the home-assistant container and then start the ozwcp container.  Apparently they cannot run at the same time (perhaps because they both are accessing the same zwcfg_xxxxxxxxxx.xml file

Run this to run the docker container for ozwcp

<pre><code>$ sudo docker run -d --name ozw-cp -u 0 -p 8008:8008 --device /dev/ttyACM0:/dev/zwave \  
-v /home/tom/haconfig/zwcfg_0xcc9dcab4.xml:/home/ozwcp_user/open-zwave-control-panel/zwcfg_0xcc9dcab4.xml \  
openzwave/openzwave-control-panel
</code></pre>

This assumes you will set your configuration.yaml file up for zwave as
<pre><code>#zwave configuration  
zwave:
  usb_path:  /dev/zwave  
  </code></pre>
  
This is because you told Docker to connect <code>/dev/zwave</code> in the container to <code>/dev/ttyACM0</code> on the host and the <strong><em>container</em></strong> is using what is in configuration.yaml

You will also use <code>/dev/zwave</code> when initializing the ozwcp for the same reason
