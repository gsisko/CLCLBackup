<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>2018-11-08-Mixed_Mode_Steering_FAQ</title>
    <style>.emoji {
  max-width: 1em !important;
}
del {
  text-decoration: none;
  position: relative;
}
del::after {
  border-bottom: 1px solid black;
  content: '';
  left: 0;
  position: absolute;
  right: 0;
  top: 50%;
}
ul.contains-task-list li.task-list-item {
  position: relative;
  list-style-type: none;
}
ul.contains-task-list li.task-list-item input.task-list-item-checkbox {
  position: absolute;
  transform: translateX(-100%);
  width: 30px;
}
span.critic.comment {
  position: relative;
}
span.critic.comment::before {
  content: '\1f4ac';
  position: initial;
}
span.critic.comment > span {
  display: none;
}
span.critic.comment:hover > span {
  display: initial;
  position: absolute;
  top: 100%;
  left: 0;
  border: 1px solid;
  border-radius: 5px;
  max-height: 4em;
  overflow: auto;
}
span.critic.comment:focus > span {
  display: initial;
  text-decoration: underline;
  position: initial;
  top: auto;
  left: auto;
  border: initial;
  border-radius: initial;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
  background-color: transparent;
}

body {
  overflow: initial !important;
  overflow: hidden;
  font-family: "Helvetica Neue", Helvetica, "Segoe UI", Arial, freesans, sans-serif;
  line-height: 1.6;
  word-wrap: break-word;
  padding: 30px;
  font-size: 16px;
  color: #333;
  background-color: #fff;
}
body > *:first-child {
  margin-top: 0 !important;
}
body > *:last-child {
  margin-bottom: 0 !important;
}
body a:not([href]) {
  color: inherit;
  text-decoration: none;
}
body .absent {
  color: #c00;
}
body .anchor {
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  padding-right: 6px;
  padding-left: 30px;
  margin-left: -30px;
}
body .anchor:focus {
  outline: none;
}
body h1,
body h2,
body h3,
body h4,
body h5,
body h6 {
  position: relative;
  margin-top: 1em;
  margin-bottom: 16px;
  font-weight: bold;
  line-height: 1.4;
}
body h1 .octicon-link,
body h2 .octicon-link,
body h3 .octicon-link,
body h4 .octicon-link,
body h5 .octicon-link,
body h6 .octicon-link {
  display: none;
  color: #000;
  vertical-align: middle;
}
body h1:hover .anchor,
body h2:hover .anchor,
body h3:hover .anchor,
body h4:hover .anchor,
body h5:hover .anchor,
body h6:hover .anchor {
  padding-left: 8px;
  margin-left: -30px;
  text-decoration: none;
}
body h1:hover .anchor .octicon-link,
body h2:hover .anchor .octicon-link,
body h3:hover .anchor .octicon-link,
body h4:hover .anchor .octicon-link,
body h5:hover .anchor .octicon-link,
body h6:hover .anchor .octicon-link {
  display: inline-block;
}
body h1 tt,
body h2 tt,
body h3 tt,
body h4 tt,
body h5 tt,
body h6 tt,
body h1 code,
body h2 code,
body h3 code,
body h4 code,
body h5 code,
body h6 code {
  font-size: inherit;
}
body h1 {
  padding-bottom: 0.3em;
  font-size: 2.25em;
  line-height: 1.2;
  border-bottom: 1px solid #eee;
}
body h1 .anchor {
  line-height: 1;
}
body h2 {
  padding-bottom: 0.3em;
  font-size: 1.75em;
  line-height: 1.225;
  border-bottom: 1px solid #eee;
}
body h2 .anchor {
  line-height: 1;
}
body h3 {
  font-size: 1.5em;
  line-height: 1.43;
}
body h3 .anchor {
  line-height: 1.2;
}
body h4 {
  font-size: 1.25em;
}
body h4 .anchor {
  line-height: 1.2;
}
body h5 {
  font-size: 1em;
}
body h5 .anchor {
  line-height: 1.1;
}
body h6 {
  font-size: 1em;
  color: #777;
}
body h6 .anchor {
  line-height: 1.1;
}
body p,
body blockquote,
body ul,
body ol,
body dl,
body table,
body pre {
  margin-top: 0;
  margin-bottom: 16px;
}
body hr {
  height: 4px;
  padding: 0;
  margin: 16px 0;
  background-color: #e7e7e7;
  border: 0 none;
}
body ul,
body ol {
  padding-left: 2em;
}
body ul.no-list,
body ol.no-list {
  padding: 0;
  list-style-type: none;
}
body ul ul,
body ul ol,
body ol ol,
body ol ul {
  margin-top: 0;
  margin-bottom: 0;
}
body li > p {
  margin-top: 16px;
}
body dl {
  padding: 0;
}
body dl dt {
  padding: 0;
  margin-top: 16px;
  font-size: 1em;
  font-style: italic;
  font-weight: bold;
}
body dl dd {
  padding: 0 16px;
  margin-bottom: 16px;
}
body blockquote {
  padding: 0 15px;
  color: #777;
  border-left: 4px solid #ddd;
}
body blockquote > :first-child {
  margin-top: 0;
}
body blockquote > :last-child {
  margin-bottom: 0;
}
body table {
  display: block;
  width: 100%;
  overflow: auto;
  word-break: normal;
  word-break: keep-all;
}
body table th {
  font-weight: bold;
}
body table th,
body table td {
  padding: 6px 13px;
  border: 1px solid #ddd;
}
body table tr {
  background-color: #fff;
  border-top: 1px solid #ccc;
}
body table tr:nth-child(2n) {
  background-color: #f8f8f8;
}
body img {
  max-width: 100%;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
body .emoji {
  max-width: none;
}
body span.frame {
  display: block;
  overflow: hidden;
}
body span.frame > span {
  display: block;
  float: left;
  width: auto;
  padding: 7px;
  margin: 13px 0 0;
  overflow: hidden;
  border: 1px solid #ddd;
}
body span.frame span img {
  display: block;
  float: left;
}
body span.frame span span {
  display: block;
  padding: 5px 0 0;
  clear: both;
  color: #333;
}
body span.align-center {
  display: block;
  overflow: hidden;
  clear: both;
}
body span.align-center > span {
  display: block;
  margin: 13px auto 0;
  overflow: hidden;
  text-align: center;
}
body span.align-center span img {
  margin: 0 auto;
  text-align: center;
}
body span.align-right {
  display: block;
  overflow: hidden;
  clear: both;
}
body span.align-right > span {
  display: block;
  margin: 13px 0 0;
  overflow: hidden;
  text-align: right;
}
body span.align-right span img {
  margin: 0;
  text-align: right;
}
body span.float-left {
  display: block;
  float: left;
  margin-right: 13px;
  overflow: hidden;
}
body span.float-left span {
  margin: 13px 0 0;
}
body span.float-right {
  display: block;
  float: right;
  margin-left: 13px;
  overflow: hidden;
}
body span.float-right > span {
  display: block;
  margin: 13px auto 0;
  overflow: hidden;
  text-align: right;
}
body code,
body tt {
  padding: 0;
  padding-top: 0.2em;
  padding-bottom: 0.2em;
  margin: 0;
  font-size: 85%;
  background-color: rgba(0, 0, 0, 0.04);
  border-radius: 3px;
}
body code:before,
body tt:before,
body code:after,
body tt:after {
  letter-spacing: -0.2em;
  content: "\00a0";
}
body code br,
body tt br {
  display: none;
}
body del code {
  text-decoration: inherit;
}
body pre > code {
  padding: 0;
  margin: 0;
  font-size: 100%;
  word-break: normal;
  white-space: pre;
  background: transparent;
  border: 0;
}
body .highlight {
  margin-bottom: 16px;
}
body .highlight pre,
body pre {
  padding: 16px;
  overflow: auto;
  font-size: 85%;
  line-height: 1.45;
  background-color: #f7f7f7;
  border-radius: 3px;
}
body .highlight pre {
  margin-bottom: 0;
  word-break: normal;
}
body pre {
  word-wrap: normal;
}
body pre code,
body pre tt {
  display: inline;
  max-width: initial;
  padding: 0;
  margin: 0;
  overflow: initial;
  line-height: inherit;
  word-wrap: normal;
  background-color: transparent;
  border: 0;
}
body pre code:before,
body pre tt:before,
body pre code:after,
body pre tt:after {
  content: normal;
}
body kbd {
  display: inline-block;
  padding: 3px 5px;
  font-size: 11px;
  line-height: 10px;
  color: #555;
  vertical-align: middle;
  background-color: #fcfcfc;
  border: solid 1px #ccc;
  border-bottom-color: #bbb;
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 #bbb;
}
span.critic.comment > span {
  background-color: #fff;
}
a {
  color: #337ab7;
}

.bracket-matcher .region {
  border-bottom: 1px dotted lime;
  position: absolute;
}
.line-number.bracket-matcher.bracket-matcher {
  color: #969896;
  background-color: #dbdde0;
}

.spell-check-misspelling .region {
  border-bottom: 2px dotted rgba(255, 51, 51, 0.75);
}
.spell-check-corrections {
  width: 25em !important;
}

@keyframes RotatingBackground {
  0% {
    background-position-x: 0%;
  }
  100% {
    background-position-x: 100%;
  }
}

.debugger-breakpoint-icon::before,
.debugger-shadow-breakpoint-icon::before {
  font-family: 'Octicons Regular';
  font-weight: normal;
  font-style: normal;
  display: inline-block;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  text-decoration: none;
  font-size: 130%;
  width: 130%;
  height: 130%;
  content: "\f052";
}
.debugger-breakpoint-icon,
.debugger-breakpoint-icon-disabled,
.debugger-breakpoint-icon-unresolved,
.debugger-breakpoint-icon-conditional,
.debugger-shadow-breakpoint-icon {
  text-align: center;
  display: block;
  width: 0.8em;
  cursor: pointer;
}
.debugger-breakpoint-icon-nonconditional {
  color: #6494ed;
}
.debugger-breakpoint-icon-conditional {
  color: #e2c08d;
}
.debugger-breakpoint-icon-disabled {
  position: relative;
  top: -4px;
  left: 2px;
}
.debugger-breakpoint-icon-disabled::before {
  font-family: 'Octicons Regular';
  font-weight: normal;
  font-style: normal;
  display: inline-block;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  text-decoration: none;
  font-size: 78%;
  width: 78%;
  height: 78%;
  content: "\f084";
}
.debugger-breakpoint-icon-unresolved {
  position: relative;
  top: -2px;
}
.debugger-breakpoint-icon-unresolved::before {
  font-family: 'Octicons Regular';
  font-weight: normal;
  font-style: normal;
  display: inline-block;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  text-decoration: none;
  font-size: 80%;
  width: 80%;
  height: 80%;
  content: "\f0e8";
}
.debugger-shadow-breakpoint-icon {
  color: rgba(100, 148, 237, 0.4);
}
.debugger-current-line-highlight {
  background: linear-gradient(to bottom, rgba(15, 130, 230, 0.8) 0%, rgba(15, 130, 230, 0.8) 5%, rgba(15, 130, 230, 0.3) 5%, rgba(15, 130, 230, 0.3) 95%, rgba(15, 130, 230, 0.8) 95%, rgba(15, 130, 230, 0.8) 100%);
}

.gutter[gutter-name=diagnostics-gutter] {
  width: 0.7em;
}
.diagnostics-gutter-ui-item {
  display: flex;
}
.diagnostics-gutter-ui-item .icon {
  display: flex;
  width: 0.7em;
  height: 0.7em;
  font-size: 0.7em;
  align-self: center;
}
.diagnostics-gutter-ui-item .icon::before {
  width: 1em;
  height: 1em;
  font-size: 1em;
  margin: 0;
  align-self: center;
}
.diagnostics-gutter-ui-item.diagnostics-gutter-ui-gutter-info,
.diagnostics-gutter-ui-item.diagnostics-gutter-ui-gutter-review {
  color: #6494ed;
}
.diagnostics-gutter-ui-item.diagnostics-gutter-ui-gutter-error {
  color: #ff6347;
}
.diagnostics-gutter-ui-item.diagnostics-gutter-ui-gutter-action,
.diagnostics-gutter-ui-item.diagnostics-gutter-ui-gutter-warning {
  color: #e2c08d;
}

pre.editor-colors,pre.editor-colors {
  background-color: #f1f1f1;
  color: #000000;
}
pre.editor-colors .bracket-matcher .region,pre.editor-colors .bracket-matcher .region {
  border-bottom: 1px solid #000000;
  box-sizing: border-box;
  border-color: #000000;
  background: #000000;
  opacity: 0.15;
}
pre.editor-colors .wrap-guide,pre.editor-colors .wrap-guide {
  background-color: #282a2e;
}
pre.editor-colors .indent-guide,pre.editor-colors .indent-guide {
  color: #ccc;
}
pre.editor-colors .invisible-character,pre.editor-colors .invisible-character {
  color: #373b41;
}
pre.editor-colors .gutter,pre.editor-colors .gutter {
  background-color: #f1f1f1;
  color: #969896;
}
pre.editor-colors .gutter .line-number.cursor-line,pre.editor-colors .gutter .line-number.cursor-line {
  background-color: #dbdde0;
  color: #969896;
}
pre.editor-colors .gutter .line-number.cursor-line-no-selection,pre.editor-colors .gutter .line-number.cursor-line-no-selection {
  color: #969896;
}
pre.editor-colors .gutter .line-number.folded,pre.editor-colors .gutter .line-number.folded,
pre.editor-colors .gutter .line-number:after,pre.editor-colors .gutter .line-number:after,
pre.editor-colors .fold-marker:after,pre.editor-colors .fold-marker:after {
  color: #969896;
}
pre.editor-colors .invisible,pre.editor-colors .invisible {
  color: #000000;
}
pre.editor-colors .cursor,pre.editor-colors .cursor {
  color: #000000;
}
pre.editor-colors .selection .region,pre.editor-colors .selection .region {
  background-color: #dbdde0;
}
pre.editor-colors .search-results .syntax--marker .region,pre.editor-colors .search-results .syntax--marker .region {
  background-color: #000000;
  border: 1px solid #000000;
}
pre.editor-colors .search-results .syntax--marker.current-result .region,pre.editor-colors .search-results .syntax--marker.current-result .region {
  border: 12px solid #373b41;
}
.syntax--comment {
  color: #68906c;
}
.syntax--keyword {
  color: #272ae2;
}
.syntax--keyword.syntax--operator {
  color: #000000;
}
.syntax--keyword.syntax--other.syntax--special-method {
  color: #272ae2;
}
.syntax--keyword.syntax--other.syntax--unit {
  color: #b97d2d;
}
.syntax--storage.syntax--type {
  color: #0b99dd;
}
.syntax--constant {
  color: #0b99dd;
}
.syntax--constant.syntax--character.syntax--escape {
  color: #b97d2d;
}
.syntax--variable {
  color: #000000;
}
.syntax--variable.syntax--interpolation {
  color: #bf4040;
}
.syntax--variable.syntax--parameter.syntax--function {
  color: #000000;
}
.syntax--invalid.syntax--illegal {
  background-color: #cc6666;
  color: #f1f1f1;
}
.syntax--string {
  color: #68906c;
}
.syntax--string.syntax--regexp {
  color: #0b99dd;
}
.syntax--string.syntax--regexp .syntax--source.syntax--ruby.syntax--embedded {
  color: #b97d2d;
}
.syntax--string.syntax--other.syntax--link {
  color: #cc6666;
}
.syntax--punctuation.syntax--definition.syntax--comment {
  color: #969896;
}
.syntax--punctuation.syntax--definition.syntax--string {
  color: #68906c;
}
.syntax--punctuation.syntax--definition.syntax--parameters,
.syntax--punctuation.syntax--definition.syntax--variable,
.syntax--punctuation.syntax--definition.syntax--array {
  color: #000000;
}
.syntax--punctuation.syntax--definition.syntax--heading,
.syntax--punctuation.syntax--definition.syntax--identity {
  color: #272ae2;
}
.syntax--punctuation.syntax--definition.syntax--bold {
  color: #f0c674;
  font-weight: bold;
}
.syntax--punctuation.syntax--definition.syntax--italic {
  color: #775bbb;
  font-style: italic;
}
.syntax--punctuation.syntax--section.syntax--embedded {
  color: #bf4040;
}
.syntax--support.syntax--class {
  color: #f0c674;
}
.syntax--support.syntax--function {
  color: #9e1313;
}
.syntax--support.syntax--function.syntax--any-method {
  color: #272ae2;
}
.syntax--entity.syntax--name.syntax--function {
  color: #000000;
}
.syntax--entity.syntax--name.syntax--class,
.syntax--entity.syntax--name.syntax--type.syntax--class {
  color: #f0c674;
}
.syntax--entity.syntax--name.syntax--section {
  color: #272ae2;
}
.syntax--entity.syntax--name.syntax--tag {
  color: #cc6666;
  text-decoration: none;
}
.syntax--entity.syntax--other.syntax--attribute-name {
  color: #272ae2;
}
.syntax--entity.syntax--other.syntax--attribute-name.syntax--id {
  color: #272ae2;
}
.syntax--meta.syntax--class {
  color: #f0c674;
}
.syntax--meta.syntax--link {
  color: #b97d2d;
}
.syntax--meta.syntax--require {
  color: #272ae2;
}
.syntax--meta.syntax--selector {
  color: #775bbb;
}
.syntax--meta.syntax--separator {
  background-color: #373b41;
  color: #000000;
}
.syntax--none {
  color: #000000;
}
.syntax--markup.syntax--bold {
  color: #b97d2d;
  font-weight: bold;
}
.syntax--markup.syntax--changed {
  color: #775bbb;
}
.syntax--markup.syntax--deleted {
  color: #cc6666;
}
.syntax--markup.syntax--italic {
  color: #775bbb;
  font-style: italic;
}
.syntax--markup.syntax--heading .syntax--punctuation.syntax--definition.syntax--heading {
  color: #272ae2;
}
.syntax--markup.syntax--inserted {
  color: #68906c;
}
.syntax--markup.syntax--list {
  color: #cc6666;
}
.syntax--markup.syntax--quote {
  color: #68906c;
}
.syntax--markup.syntax--raw.syntax--inline {
  color: #68906c;
}
.syntax--source.syntax--gfm .syntax--markup {
  -webkit-font-smoothing: auto;
}
.syntax--source.syntax--gfm .syntax--markup.syntax--heading {
  color: #68906c;
}
pre.editor-colors[mini] .scroll-view,pre.editor-colors .scroll-view {
  padding-left: 1px;
}
.syntax--js .syntax--storage {
  color: #272ae2;
}
.syntax--js.syntax--support.syntax--class {
  color: #e69e11;
}
.syntax--js.syntax--support.syntax--constant {
  color: #9e1313;
}

/*
 * Your Stylesheet
 *
 * This stylesheet is loaded when Atom starts up and is reloaded automatically
 * when it is changed and saved.
 *
 * Add your own CSS or Less to fully customize Atom.
 * If you are unfamiliar with Less, you can read more about it here:
 * http://lesscss.org
 */
/*
 * Examples
 * (To see them, uncomment and save)
 */
</style>

  </head>
  <body>
    <h2 id="q-how-do-i-steer-with-a-single-joystick-on-a-dual-motor-controller">Q: How do I steer with a single joystick on a dual motor controller?</h2>
<p>By default, our controllers will control a <a href="https://en.wikipedia.org/wiki/Differential_wheeled_robot">differential drive</a> in tank mode. Using Mixed mode steering, you can control both the speed and the steering with a single joystick.</p>
<h2 id="steps-to-configure-mixed-mode-steering">Steps to Configure mixed Mode Steering</h2>
<ul>
<li><p>Make sure that you have Mixed Mode steering set in General Drop down menu of the Power Output section in the Configuration tab of Roborun+: <img src="assets\markdown-img-paste-20181108094121295.png"></p></li>
<li><p>Make sure you remember to Save the configuration to the controller:</p></li>
</ul>
<p><img src="assets\markdown-img-paste-20181108094223488.png"></p>
<h2 id="have-more-questions">Have More Questions?</h2>
<p>Please reference <strong>SECTION 7: Motor Operating Features and Options</strong> of our <a href="https://www.roboteq.com/index.php/docman/motor-controllers-documents-and-files/documentation/user-manual/272-roboteq-controllers-user-manual-v17/file">User Manual</a> for in depth documentation of Mixed Mode Steering. If you still have questions please reach out to <a href="mailto:techsupport@roboteq.com">techsupport@roboteq.com</a>.</p>
<!--START FAQ Footer -->
<!-- Reference Links -->
<!-- Application Notes -->
<!-- FAQs -->
<!-- 3rd Party Links -->
<!-- For emails, prodcuct pages should be the default link for product names -->
<!-- Single Channel Induction -->
<!-- Single Channel Brushless -->
<!-- Brushless -->
<!-- Single Channel Brushed -->
<!-- Brushed -->
<!-- MagSensors -->
<!-- END FAQ Footer -->

  </body>
</html>
