# Appendix B: Maqamat Score Notes

Each staff below is rendered live from a MusicXML file in `scores/` using
[OpenSheetMusicDisplay](https://opensheetmusicdisplay.org/). Scale shown
ascending then descending (violin, treble clef).

<div id="osmd-rast" class="osmd-score"></div>
<div id="osmd-hijaz" class="osmd-score"></div>
<div id="osmd-sikah" class="osmd-score"></div>
<div id="osmd-nikriz" class="osmd-score"></div>
<div id="osmd-bayati" class="osmd-score"></div>
<div id="osmd-nahawand" class="osmd-score"></div>
<div id="osmd-kurd" class="osmd-score"></div>
<div id="osmd-ajam" class="osmd-score"></div>
<div id="osmd-saba" class="osmd-score"></div>

## Sayr (Performance) Examples

Longer phrases illustrating the traditional five-part Sayr shape — establish
tonic, ascend to the Ghammaz, explore the upper jins, return, and resolve
with a Qafla.

<div id="osmd-rast-sayr" class="osmd-score"></div>
<div id="osmd-hijaz-sayr" class="osmd-score"></div>
<div id="osmd-nikriz-sayr" class="osmd-score"></div>

<script src="https://cdn.jsdelivr.net/npm/opensheetmusicdisplay@1.8.6/build/opensheetmusicdisplay.min.js"></script>
<script>
(function () {
  var scores = [
    ["osmd-rast",     "scores/rast.musicxml"],
    ["osmd-hijaz",    "scores/hijaz.musicxml"],
    ["osmd-sikah",    "scores/sikah.musicxml"],
    ["osmd-nikriz",   "scores/nikriz.musicxml"],
    ["osmd-bayati",   "scores/bayati.musicxml"],
    ["osmd-nahawand", "scores/nahawand.musicxml"],
    ["osmd-kurd",     "scores/kurd.musicxml"],
    ["osmd-ajam",     "scores/ajam.musicxml"],
    ["osmd-saba",     "scores/saba.musicxml"],
    ["osmd-rast-sayr",   "scores/rast-sayr.musicxml"],
    ["osmd-hijaz-sayr",  "scores/hijaz-sayr.musicxml"],
    ["osmd-nikriz-sayr", "scores/nikriz-sayr.musicxml"]
  ];

  scores.forEach(function (entry) {
    var containerId = entry[0], xmlPath = entry[1];
    var el = document.getElementById(containerId);
    if (!el) return;
    var osmd = new opensheetmusicdisplay.OpenSheetMusicDisplay(el, {
      autoResize: true,
      drawTitle: true
    });
    osmd.load(xmlPath).then(function () {
      osmd.render();
    }).catch(function (err) {
      el.innerHTML = "<p style='color:red'>Could not load " + xmlPath + ": " + err + "</p>";
    });
  });
})();
</script>
