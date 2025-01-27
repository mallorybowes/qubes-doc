---
lang: en
layout: doc
permalink: /doc/updating-qubes-os/
ref: 200
title: Updating Qubes OS
---

Updating Qubes OS
=================

*This page is about updating your system while staying on the same [supported version of Qubes OS](/doc/supported-versions/#qubes-os).
If you're instead looking to upgrade from your current version of Qubes OS to a newer version, see the [Upgrade Guides](/doc/upgrade/).*

<div class="alert alert-danger" role="alert">
  <i class="fa fa-exclamation-triangle"></i>
  <b>Warning:</b> Updating with direct commands such as <code>qubes-dom0-update</code>, <code>dnf update</code>, and <code>apt update</code> is <b>not</b> recommended, since these bypass built-in Qubes OS update security measures.
  Instead, we strongly recommend using the <b>Qubes Update</b> tool or its command-line equivalents, as described below.
  (By contrast, <a href="/doc/software-update-domu/#installing-software-in-templatevms">installing</a> packages using direct package manager commands is fine.)
</div>

It is very important to keep your Qubes OS system up-to-date to ensure you have the latest [security](/security/) updates, as well as the latest non-security enhancements and bug fixes.

Fully updating your Qubes OS system means updating:

- [Dom0](/doc/software-update-dom0/)
- [TemplateVMs](/doc/software-update-domu/#updating-software-in-templatevms)
- [StandaloneVMs](/doc/software-update-domu/#standalonevms) (if you have any)

You can accomplish this using the **Qubes Update** tool.

[![Qubes Update](/attachment/wiki/QubesScreenshots/r4.0-software-update.png)](/attachment/wiki/QubesScreenshots/r4.0-software-update.png)

By default, the Qubes Update tool will appear as an icon in the Notification Area when updates are available.

[![Qube Updates Available](/attachment/wiki/QubesScreenshots/r4.0-qube-updates-available.png)](/attachment/wiki/QubesScreenshots/r4.0-qube-updates-available.png)

However, you can also start the tool manually by selecting it in the Applications Menu under "System Tools."
Even if no updates have been detected, you can use this tool to check for updates manually at any time by selecting "Enable updates for qubes without known available updates," then selecting all desired items from the list and clicking "Next."

<div class="alert alert-info" role="alert">
  <i class="fa fa-info-circle"></i>
  <b>Note:</b> For the command-line equivalents of using the <b>Qubes Update</b> tool, see the Salt formulae <a href="/doc/salt/#updatequbes-dom0"><code>update.qubes-dom0</code></a> and <a href="/doc/salt/#updatequbes-vm"><code>update.qubes-vm</code></a>.
</div>

The final step is to make sure that all of your VMs are running a supported operating system so that they're all receiving upstream security updates.
For example, you might be using a [Fedora TemplateVM](/doc/templates/fedora/).
The [Fedora Project](https://getfedora.org/) is independent of the Qubes OS Project.
They set their own [schedule](https://fedoraproject.org/wiki/Fedora_Release_Life_Cycle#Maintenance_Schedule) for when each Fedora release reaches [end-of-life](https://fedoraproject.org/wiki/End_of_life) (EOL).
You can always find out when an operating system reaches EOL from the upstream project that maintains it, but we also make EOL [announcements](/news/categories/#announcements) and publish guides for official TemplateVM operating systems as a convenience to Qubes users.
When this happens, you should make sure to follow the guide to upgrade to a supported version of that operating system (see the [Fedora upgrade guides](/doc/templates/fedora/#upgrading) and the [Debian upgrade guides](/doc/templates/debian/#upgrading)).
The one exception is dom0, which [doesn't have to be upgraded](/doc/supported-versions/#note-on-dom0-and-eol).

