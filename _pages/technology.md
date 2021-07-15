---
permalink: /technology/
title: Technology 4 All
---
<div class="responsive-wrap" markdown="0">
  <script>
  navigator.mediaDevices.getUserMedia({ audio: true })
      .then(function(stream) {
        console.log('You let me use your mic!')
      })
      .catch(function(err) {
        console.log('No mic for you!')
      });
  </script>
  <script src='https://meet.jit.si/external_api.js'></script>
  <script>
    const domain = 'meet.jit.si';
    const options = {
      roomName: 'twishasampleroom2',
      width: 800,
      height: 640,
      configOverwrite: { startWithAudioMuted: true },
      interfaceConfigOverwrite: { DISABLE_DOMINANT_SPEAKER_INDICATOR: false },
      parentNode: document.querySelector('#meet')
    };
  const api = new JitsiMeetExternalAPI(domain, options);
  </script>
  <iframe id="conf" allow="camera *;microphone *;fullscreen *;autoplay *" src="https://meet.jit.si/twishasampleroom2" width="800" height="640" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
  <script>
    el=document.getElementById("conf");
    el.src="https://ayeai.xyx";
    el.contentDocument.location.reload(true);
  </script>
</div>

