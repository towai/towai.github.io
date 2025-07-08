<head>
	<!--
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	-->
	<link href="https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible&display=swap" rel="stylesheet">
	<style>
		body {
			background-color: #023;
			color: #bed;
			padding-top: 1rem;
			font-family: 'Atkinson Hyperlegible';
			text-align: justify;
			text-shadow: 1px 0px 1px black;
		}
		a:link {
			color: #3deadf;
		}
		a:visited {
			color: #2ba5ed;
		}/*
		h2 {
			border-right-width: 2px;
			border-left-width: 2px;
			border-radius: 5px;
			border-color: #2ba5ed;
			width: max-content;
		}*/
		h3 {
			margin-bottom: 0.5rem;
		}
		p, h4 {
			max-width: 1200px;
		}
		p {
			text-align: justify;
			margin: 0.5rem auto;
		}
		hr {
			margin: 1rem 9rem;
			border-radius: 5px;
			border-color: #2ba5ed;
			border-width: 2px;
			min-height: 5px;
			max-width: 1200px;
			border-style: solid;
		}
		hr.top {
			border-top-width: 0;
		}
		hr.bot {
			border-bottom-width: 0;
		}
		.cols {
			display: flex;
			margin: 0.5rem 0rem;
			max-width: 1200px;
		}
		.cols > h3 {
			float: left;
			width: 15%;
			margin: auto 1rem;
			position: relative;
			top: 50%;
			text-align: right;
		}
		.cols > p, .cols > h4 {
			margin: 0.25rem 0;
			width: 85%;
			vertical-align: middle;
			text-align: left;
		}
		.cols:after {
			content: "";
			display: table;
			clear: both;
		}
	</style>
</head>

# Surf Zones for Momentum Mod

### If you don't care about the details of the different packs, you can just go to the [MEGA folder][MEGAfolder].

These packs of .zon map definitions are converted from various sources for the latest .zon definition format as of 22 January, 2023.
They are provided without any editing and not very much testing.
So if you find a map with broken zones in one pack, see if it's defined in another and give that version a try instead.

As of 05 October, 2023, I haven't tested any of these with the latest version,
but they should still be compatible with version 0.9.21 (latest public release).
At the very least, glancing at the docs repo I haven't been able to identify any changes to the zone format, much less breaking changes.

To install, just extract into `%game directory%/momentum/zones`
(be sure not to let Windows or 7zip or whatever else make an additional subfolder within `zones/`!)

You can have the [source for the converter][converter_zip] if you have a set of your own you want to convert,
(like if you have/had your own server or something with its own maplist)
but know it's a Godot 4 project since that's just easiest for me to write and iterate with,
(especially since it comes with stuff for file handling, parsing CSV lines, etc).
<sup>Now seems to be as good a time as any to learn Godot scripting! :))</sup>
Also, if it's in a different format than the few I tested with, you're on your own <span title="with regard to">w.r.t</span> adding support,
though I tried to at least make the conversion process modular & extendable within reason.
This converter *does not* handle SQL files directly -- you have to convert the zones table into a CSV sheet
(like with [this tool](https://sqlitebrowser.org/), for example)
while keeping the column labels as the first row.

<hr class="top" />

## [wayne3288.zip][wayne3288_zip]

<div class="cols">

### Source
Converted from a collection of zone definitions in an older .zon format
that was <a href="https://github.com/dPexxIAM/Momentum-surf-zones">made available on GitHub</a>.
</div><div class="cols">

### Notes
The source format supports multiple stages, but apparently does not support multiple tracks.
</div><div class="cols">

### Map Count
#### 200

</div>

## [Flow Surf.zip][FlowSurf_zip]

</div><div class="cols">

### Source
Converted from a SQL table provided in a <a href="https://nulledbb.com/thread-Surf-Gamemode">starter pack</a>
for people starting a new surf GMod server.
</div><div class="cols">

### Notes
The source format supports multiple tracks, but apparently does not support stages,
only start and end zones (see: surf_beginner, surf_rookie).
</div><div class="cols">

### Map Count
#### 103

</div>

# ckSurf/SurfTimer format

<p style="text-align: center;">This format supports both multiple tracks and multiple stages to a track.

## [.enjoy.zip][.enjoy_zip]

<div class="cols">

### Source
Converted from a ZoneDB SQL table graciously provided by .enjoy
(same person who maintains the [directory of zone defs](http://nnsurf.site.nfoservers.com/Momentum/) linked in the FAQ)
on the Momentum Discord server.
</div><div class="cols">

### Notes
The source format is the same as the format used in the latest version of ckSurf.
There's a few maps with sort of borked definitions I noticed (surf_mushroom_ksf, surf_fruits, surf_sluice)
but the issues are present in the SQL table and aren't due to the conversion.
</div><div class="cols">

### Map Count
#### 506
</div>

## [SurfTimer.zip][SurfTimer_zip]

<div class="cols">

### Source
Converted from a ZoneDB SQL table [available in the GitHub repo](https://raw.githubusercontent.com/surftimer/SurfTimer/dev/scripts/mysql-files/ck_zones.sql) of the SurfTimer plugin for CS:GO surf servers.
</div><div class="cols">

### Notes
A continuation of the ckSurf format, this pack's source format has a few more fields, chiefly a `prespeed` field, but it's almost always 350, the default.
Some zones have a value of 0 in that column, in which case they were converted with `limitingspeed` (whether to cap player speed on exiting the zone) disabled.
</div><div class="cols">

### Map Count
#### 744
</div>

<hr class="bot" />

<small>読んで　くれて　ありがとう</small>

[MEGAfolder]: https://mega.nz/folder/0ZJzxRZS#Ey1BTegBVngpfzMo-GuVyw "MEGA folder"
[.enjoy_zip]: https://mega.nz/file/AYAXgJgS#RYEPYGiu_2z1ttkUE9yBQ39pfMwwuMpOqzVXeQFZduA
[converter_zip]: https://mega.nz/file/kV4jnLDL#fzjazicVjQL_-iFf2rhCRO44qQLRhYqG4DPhg0iOlDE
[FlowSurf_zip]: https://mega.nz/file/sZASgDJR#evf8B3FQjlX0mnrmGrvxfH88_C5XMQ8UhkuEoemIuSs
[SurfTimer_zip]: https://mega.nz/file/1ZBxjYoR#IdJNhEBzD5Z3ibk2CgV9piFRG7cUBFqI1KUmdXvWf4c
[wayne3288_zip]: https://mega.nz/file/RQRhnDoa#aPQiUoQ8ic47ASQFEEC_ArVFcrg0IIHdhvk4yGnwK8M
