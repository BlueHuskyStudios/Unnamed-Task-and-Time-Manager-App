---
layout: default

title: Overview
app-bar:
    trailing-control:
        target:
---

# Ultimate Task and Time Management App #
I have lots of ideas for a task-and-time management app. They're laid-out herein.

<aside><a href="https://github.com/BlueHuskyStudios/Unnamed-Task-and-Time-Manager-App/">GitHub Repo</a></aside>


{% assign ids = "Structure,Priority,Cloud,Automation,Delightful-Features,Cross-Platform" | split: "," %}
{% assign titles = "Structure,Priority,Cloud,Automation,Delightful Features,Cross-Platform" | split: "," %}


{% include jump-pills.html
    ids=ids
	titles=titles
%}



{% include_relative section/structure.md %}



<section id="Section_Priority">
	<h2 id="Priority"><a href="#Section_Priority">Priority</a></h2>
	<p>A cascading priority system will allow users to let themselves, others with viewing permission, and the
		app's automation to understand how to prioritize things.</p>
	<ol>
		<li>User preferences dictate the default priority (first install starts with Medium).</li>
		<li>Updating that preference gives the option to cascade the change or leave existing tasks at their
			current priority.</li>
		<li>Each group has its own priority. By default this is the same as the user's preference.</li>
		<li>Each tasklist group has its own priority. By default this is the same as its group's.</li>
		<li>Each item in a tasklist has its own priority. By default this is the same as the tasklist's.</li>
	</ol>

	<section id="Section_Priority_Customization">
		<h3 id="Priority_Customization"><a href="#Section_Priority_Customization">Priority tiers can be customized</a></h3>
		<p>Priorities have arbitrary numbers associated (string-parsed decimal fractions). Priorities have
			arbitrary colors associated.</p>
		<p>Defaults:</p>
		<ol>
			<li>Immediate - 1000</li>
			<li>Very High - 800</li>
			<li>High - 700</li>
			<li>Medium - 500</li>
			<li>Low - 300</li>
			<li>Very Low - 200</li>
			<li>On hold - 100</li>
			<li>Won't happen - 0</li>
		</ol>
	</section>
</section>



<section id="Section_Cloud">
	<h2 id="Cloud"><a href="#Section_Cloud">Cloud</a></h2>
	<ul>
		<li>All data will be saved to a set of servers. That said, a 3rd-party, personal, or local (on-same-machine)
			server can be used if you want.</li>
		<li>Data will be encrypted in storage and transmission</li>
		<li>You will be able to share and collaborate on groups or tasklists with others using the same server set.
			You cannot share or collaborate on worlds; those are for separation of personal mindsets.</li>
	</ul>
</section>



<section id="Section_Automation">
	<h2 id="Automation"><a href="#Section_Automation">Automation</a></h2>

	<blockquote>This app will have a strong emphasis on automatability.</blockquote>

	<section id="Section_Automation_Other-to-app">
		<h3 id="Automation_Other-to-app"><a href="#Section_Automation_Other-to-app">Other-to-app hierarchy</a></h3>
		<ol>
			<li>Platform-specific automation events are caught by a specialized plugin for each platform. This
				allows many approaches, such as Tasker, Apple Events, network-pushed events, etc. to all automate
				the app.</li>
			<li>Plugins will conform to a specific API that describes all the ways the app can be automated.</li>
			<li>The app's central automation service will listen for events fired by plugins via the API via
				sockets, and automate the app.</li>
		</ol>
	</section>


	<section id="Section_Automation_App-to-other">
		<h3 id="Automation_App-to-other"><a href="#Section_Automation_App-to-other">App-to-other</a></h3>
		<ol>
			<li>Internal events that are registered as triggering external events will fire to the central
				automation service.</li>
			<li>The automation service will pass these events on to any plugins that are registered as listening
				for them via a similar API as the one used for other-to-app automation.</li>
			<li>The plugin will then perform the action it deems necessary upon receiving the event.</li>
		</ol>
	</section>


	<section id="Section_Automation_Preinstalled-plugins">
		<h3 id="Automation_Preinstalled-plugins"><a href="#Section_Automation_Preinstalled-plugins">Preinstalled plugins</a></h3>
		<p>Out-of-the-box, the app will come with plugins for sending notifications to the OS, receiving location
			change events, etc.</p>
	</section>
</section>



<section id="Section_UI">
	<h2 id="UI"><a href="#Section_UI">UI</a></h2>
	<p>The UI hasn't been fleshed-out, but it's absolutely crucial that it is made beautiful, delightful, and
		intuitive. If not, the complexity of the functionality may be miscommunicated, daunting, or just
		confusing.</p>

	<section id="Section_UI_Notifications">
		<h3 id="UI_Notifications"><a href="#Section_UI_Notifications">Notifications</a></h3>
		<p>Notifications are very important in a task management app. In fact, one might argue they're the
			 <em>most</em> important. This means they <em>must</em> be just right, or this app will fail.</p>

		 <ul>
			 <li>Always use platform-native notifications; these are what the user expects</li>
			 <li>Allow notifications to occur <em>before</em> the due date, up to some arbitrary amount the user
				 can specify (e.g. 1 week before, 5 minutes before, etc.)</li>
		 </ul>
	</section>
</section>



<section id="Section_Delightful-Features">
	<h2 id="Delightful-Features"><a href="#Section_Delightful-Features">Delightful features</a></h2>
	<p>Delight is essential to the user enjoying the experience of using the app. Here are a few ideas for how
		this app can be more delightful:</p>

	<ul>
		<li>Location-based silencing and hiding of tasks</li>
		<li>Tiered sorting (both soft and hard), like "By completion status, then by date due, then by name, then
			by date made"</li>
		<li>Certain tasks can be "pinned to top" to guarantee they're always in your head. Maximum priority and
			imminently-due tasks can thus be set to be elevated above these priorities.</li>
		<li>Custom tags can be assigned to groups, tasklists, and tasks. These will be reflected in a Tags view and
			in search queries</li>
		<li>Completion statuses similar to priority tiers (defaults included, customs supported), but can be
			localized to a single structure</li>
		<li>Defer until another task anywhere else is completed</li>
	</ul>
</section>



<section id="Section_Cross-Platform">
	<h2 id="Cross-Platform"><a href="#Section_Cross-Platform">Cross-Platform</a></h2>
	<p>This will be available on all major platforms, using this stack:</p>

	<table class="platforms">
		<thead>
			<tr>
				<td></td>
				<th>macOS</th>
				<th>iOS</th>
				<th>Windows</th>
				<th>Linux</th>
				<th>Android</th>
				<th>Web</th>
			</tr>
		</thead>

		<tbody>
			<tr class="plat-ui plat-lib">
				<th>UI Platform</th>
				<td>Cocoa</td>
				<td>Cocoa Touch</td>
				<td colspan="2">Swing or JavaFX</td>
				<td>Material</td>
				<td>HTML+CSS</td>
			</tr>

			<tr class="plat-ui plat-lang">
				<th>UI Language</th>
				<td colspan="2" rowspan="2" class="plat-kotlin-native">Kotlin/Native</td>
				<td colspan="3" rowspan="2" class="plat-kotlin-jvm">Kotlin/JVM</td>
				<td rowspan="2" class="plat-kotlin-js">Kotlin/JS</td>
			</tr>

			<tr class="plat-logic plat-local">
				<th>Local Logic</th>
			</tr>

			<tr class="plat-logic plat-cloud">
				<th>Cloud Logic</th>
				<td colspan="6" class="plat-kotlin-js">Kotlin/JS</td>
			</tr>

			<tr class="plat-lib plat-cloud">
				<th>Cloud Platform</th>
				<td colspan="6">Node.JS</td>
			</tr>
		</tbody>
	</table>
</section>
