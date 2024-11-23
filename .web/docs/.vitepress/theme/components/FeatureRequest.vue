<script setup>
import { ref, onMounted } from 'vue';

const phid = ref('');

onMounted(() => {
  !(function (w, d, i, s) {
    function l() {
      if (!d.getElementById(i)) {
        var f = d.getElementsByTagName(s)[0],
          e = d.createElement(s);
        (e.type = 'text/javascript'),
          (e.async = !0),
          (e.src = 'https://canny.io/sdk.js'),
          f.parentNode.insertBefore(e, f);
      }
    }
    if ('function' != typeof w.Canny) {
      var c = function () {
        c.q.push(arguments);
      };
      (c.q = []),
        (w.Canny = c),
        'complete' === d.readyState
          ? l()
          : w.attachEvent
          ? w.attachEvent('onload', l)
          : w.addEventListener('load', l, !1);
    }
  })(window, document, 'canny-jssdk', 'script');

  Canny('render', {
    boardToken: 'd256f3b0-92a8-9558-9131-4f56d40dd348',
    basePath: '/guide/feedback',
    ssoToken: null,
    theme: 'auto',
  });
});
</script>

<template>
  <div data-canny />
</template>
