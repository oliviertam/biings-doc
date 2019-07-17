<div class="container wrapper has-text-centered">

<h1 class="title is-2 is-spaced">Host Biings on your server</h1>
<p class="subtitle is-5 has-text-centered has-text-grey-darker">
    You can host your own instance of Biings on your server and get unlimited integration possibilities while retaining the same Biings experience.
    Server requirements below.
</p>

<hr>

<div class="tabs is-boxed is-marginless is-centered">
    <ul class="is-borderless">
        <li class="is-active" onclick="toggleTab(1)" id="tab-1"><a>Server or Virtual machine</a></li>
        <li id="tab-2" onclick="toggleTab(2)"><a>Ports opening</a></li>
        <li id="tab-3" onclick="toggleTab(3)"><a>Browser support</a></li>
    </ul>
</div>
<div id="box-1" class="box is-large is-floating">

| Minimum requirements | |
|:-|-|
| OS | **Debian** / **Windows Server 2012** or higher |
| Processor | **Dual-Core 2GHz** |
| RAM | **8 Gb** or 4 Gb for small organisations |
| Disk space | **30 Gb** (OS excluded) |
| Database | **PostgreSQL** 8.5 or higher, **Microsoft SQL Server** |
| Web Server | **Nginx** or **Apache** |

</div>
<div id="box-2" class="box is-large is-floating is-hidden">

To allow Biings to communicate with its users, external services (e.g. insurance) and our maintenance team, the following ports must be available / open :<br><br>

| Protocol | Port | Direction |
|:-|:-|:-|
| sftp / ssh | 22 | *any* |
| http / https | 443 or 80 | *any* |
| smtp | 587 | outbound |

<br>

<p class="warn">
Biings occasionnaly makes requests to the following third-party internet services :<br>
• <strong>Gravatar</strong> : https://www.gravatar.com/<br>
• <strong>Insurance claim report services</strong> (e.g. https://sunetintg.suva.ch/sunet41/)<br>
• <strong>Intercom</strong>: https://widget.intercom.io/ (for app support only)
</p>

</div>
<div id="box-3" class="box is-large is-floating is-hidden">

When connecting to Biings from the Web, please make sure you are using one of these supported browsers, with Javascript enabled. For a smooth experience, please make sure your browser and operating system is up to date.

<hr class="is-small">

| | <img src="/media/browser_chrome.png" class="image is-64x64">Chrome | <img src="/media/browser_firefox.png" class="image is-64x64">Firefox | <img src="/media/browser_safari.png" class="image is-64x64">Safari | <img src="/media/browser_ie.png" class="image is-64x64">IE | <img src="/media/browser_opera.png" class="image is-64x64">Opera |
|-:|:-:|:-:|:-:|:-:|:-:|
| **Optimal** | **31+** | **28+** | **5.1** / **iOS 6+** | **11+** | **20+** |
| Minimum | 14 | 5 | 4 / iOS 5 | 10 | 11 |

</div>

---

<div class="has-text-centered">
    On-premises distributions are installed by our technicians 👨‍🔧<br><a href="https://www.biings.com/contact.html">Contact us</a> to get in touch.
</div>

</div>
