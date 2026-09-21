---
layout: archive
title: "CARES"
permalink: /cares/
author_profile: true
---

{% include base_path %}

<style>
.cares-lede{font-size:1.05em;line-height:1.65;max-width:46em}
.cares-pipeline{margin:2.2em 0 2.6em}
.cares-pipeline img{width:100%;height:auto;border-radius:6px}
.cares-pipeline figcaption{font-size:.82em;color:#8a8a8a;margin-top:.7em;text-align:center}
.cares-types{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:.9em;margin:1.6em 0 2.8em;padding:0;list-style:none}
.cares-types li{border-left:3px solid #d8d8d8;padding:.15em 0 .15em .85em}
.cares-types b{display:block;font-size:.78em;letter-spacing:.09em;text-transform:uppercase;margin-bottom:.25em}
.cares-types span{font-size:.92em;line-height:1.5;color:#666}
.t-pivot b{color:#b4562a}.t-pivot{border-left-color:#b4562a!important}
.t-verbal b{color:#2f6f9f}.t-verbal{border-left-color:#2f6f9f!important}
.t-behavioral b{color:#6b4c9a}.t-behavioral{border-left-color:#6b4c9a!important}
.t-ambient b{color:#5f7a62}.t-ambient{border-left-color:#5f7a62!important}
.cares-sample{margin:0 0 2.6em;padding-bottom:2.2em;border-bottom:1px solid #ececec}
.cares-sample:last-of-type{border-bottom:0}
.cares-head{display:flex;flex-wrap:wrap;align-items:baseline;gap:.6em;margin-bottom:.5em}
.cares-badge{font-size:.7em;letter-spacing:.09em;text-transform:uppercase;padding:.2em .6em;border-radius:3px;color:#fff;white-space:nowrap}
.b-pivot{background:#b4562a}.b-verbal{background:#2f6f9f}.b-behavioral{background:#6b4c9a}.b-ambient{background:#5f7a62}
.cares-where{font-size:.9em;color:#777}
.cares-where code{background:none;padding:0;font-size:1em;color:#555}
.cares-sample audio{width:100%;margin:.7em 0 1em;height:38px}
.cares-quote{font-size:.94em;line-height:1.7;color:#444;border-left:2px solid #e2e2e2;padding-left:1em;margin:0}
.cares-quote .sp{color:#999;font-weight:600;margin-right:.35em}
.cares-quote .cue{display:block;margin:.5em 0;font-size:.82em;letter-spacing:.06em;text-transform:uppercase;color:#b4562a}
.cares-note{font-size:.88em;color:#777;margin-top:.8em}
@media(prefers-color-scheme:dark){
 .cares-types span,.cares-quote{color:#b8b8b8}
 .cares-sample{border-bottom-color:#333}
 .cares-quote{border-left-color:#3a3a3a}
 .cares-where,.cares-note,.cares-pipeline figcaption{color:#8f8f8f}
 .cares-where code{color:#a5a5a5}
}
</style>

<p class="cares-lede">
CARES is a dataset of two-speaker audio scenes in which an environmental sound is placed
inside a conversation. Each sound carries a <b>reaction type</b> that the dialogue has to
realise — without ever naming the sound. Recovering that type means linking what is heard
to what the conversation does with it.
</p>

<figure class="cares-pipeline">
  <img src="{{ base_path }}/images/cares/pipeline.gif" alt="The CARES generation pipeline, stage by stage">
  <figcaption>From themes to mixed audio scenes: everything structural is drawn from a fixed seed before the first model call.</figcaption>
</figure>

## The four reaction types

<ul class="cares-types">
  <li class="t-pivot"><b>Pivot</b><span>The sound takes over. It becomes the subject for several turns.</span></li>
  <li class="t-verbal"><b>Verbal</b><span>One speaker acknowledges it in passing, then the conversation resumes.</span></li>
  <li class="t-behavioral"><b>Behavioral</b><span>Nobody mentions it, but it visibly disrupts the speaking.</span></li>
  <li class="t-ambient"><b>Ambient</b><span>Nobody reacts at all.</span></li>
</ul>

## Listen

<div class="cares-sample">
  <div class="cares-head">
    <span class="cares-badge b-pivot">Pivot</span>
    <span class="cares-where">beach · <code>watch_alarm</code> · at 48s</span>
  </div>
  <audio controls preload="none" src="{{ base_path }}/files/cares/1_pivot.mp3"></audio>
  <p class="cares-quote">
    <span class="sp">A</span>In my notes. On my phone. Which is with me at all times, so.
    <span class="cue">↓ a watch alarm goes off</span>
    <span class="sp">B</span>Hang on, was that you? Something just went off right by me.
  </p>
</div>

<div class="cares-sample">
  <div class="cares-head">
    <span class="cares-badge b-verbal">Verbal</span>
    <span class="cares-where">café · <code>chair_scraping</code> · at 72s</span>
  </div>
  <audio controls preload="none" src="{{ base_path }}/files/cares/2_verbal.mp3"></audio>
  <p class="cares-quote">
    <span class="sp">A</span>…I've told Marco he's on potatoes and he's furious about the demotion.
    <span class="cue">↓ a chair scrapes</span>
    <span class="sp">B</span>Oof, that went right through my back teeth. Sharp. Anyway, poor Marco, twenty years of stuffing rights gone in one phone call.
  </p>
  <p class="cares-note">Acknowledged, then dropped — the subject survives the interruption.</p>
</div>

<div class="cares-sample">
  <div class="cares-head">
    <span class="cares-badge b-behavioral">Behavioral</span>
    <span class="cares-where">airport · <code>security_conveyor_belt</code> · at 16s</span>
  </div>
  <audio controls preload="none" src="{{ base_path }}/files/cares/3_behavioral.mp3"></audio>
  <p class="cares-quote">
    <span class="sp">A</span>Manchester. Back Sunday. Actually, funny thing, I've got the Pixies next Friday. Dan sorted it.
    <span class="cue">↓ a security conveyor belt starts</span>
    <span class="sp">B</span>Wait, next Friday, at the… the big one, the one by the station, it's got the ugly roof, I can never… anyway, yeah, that place.
  </p>
  <p class="cares-note">The sound is never mentioned. It only shows in how the sentence comes apart.</p>
</div>

<div class="cares-sample">
  <div class="cares-head">
    <span class="cares-badge b-ambient">Ambient</span>
    <span class="cares-where">public park · <code>baby_crying</code> · at 20s</span>
  </div>
  <audio controls preload="none" src="{{ base_path }}/files/cares/4_ambient.mp3"></audio>
  <p class="cares-quote">
    <span class="sp">A</span>She sits out on that balcony with her tea and she's already got a list of things to tell me.
    <span class="cue">↓ a baby starts crying</span>
    <span class="sp">B</span>A list. Of course she does. And you just let her run through it?
  </p>
  <p class="cares-note">Clearly audible, and the conversation does not bend around it.</p>
</div>

<div class="cares-sample">
  <div class="cares-head">
    <span class="cares-badge b-pivot">Pivot</span>
    <span class="cares-where">kitchen · <code>siren_ambulance</code> · rare sound · at 33s</span>
  </div>
  <audio controls preload="none" src="{{ base_path }}/files/cares/5_pivot.mp3"></audio>
  <p class="cares-quote">
    <span class="sp">A</span>He keeps saying he's just being direct. Which, fine, be direct in the huddle. Not while I'm trying to read a hitter.
    <span class="cue">↓ an ambulance siren passes</span>
    <span class="sp">B</span>Whoa, that's right outside. That was RIGHT outside!
  </p>
  <p class="cares-note">Rare sounds are always pivots — the one case where the sound outranks the subject.</p>
</div>

## Code

The full pipeline and the evaluation harness for audio-language models are on
[GitHub](https://github.com/marcelgibier/CARES).
