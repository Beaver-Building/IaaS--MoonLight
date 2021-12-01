   

Core modules that build the Internet Explorer application/process

IEXPLORE.exe:

Parse the command line options

Specifically check if you are running in the Application Compatibility Mode

( Runs the program using settings from an earlier version of Windows. Try this setting if you know the program is designed for (or worked with) a specific version of Windows.)

Sets up the exception filter for Internet Explorer ( WER )

WININET.dll: (interface between the sockets layer and browser)

Local Cache

History

Cookie Management

Website Authentication

Data Compression/ Decompression

Http cache control

Proxy Authentication

URLMON.dll:

URL Parsing - breaking down URLs into the protocol used, address and target

Security and Zone Management - Identifies Security zones, zone assignment/ crossings, permissions

Forms request from the URL - creates the outbound data package and hands it off to WININET for transfer.

MIME (Multipurpose Internet Mail Extension) type management - examines the MIME type for data returned in an HTTP response and correlates that type with a specific Handler

Code download and management

Install on Demand (IOD)and just in time (JIT)

This core module deals with everything that is related with the browser user interface. It’s responsible by:

Windows layout and display

Frame rendering for browser application and content navigation

Control panel functions

Short cuts and favorites

Inter-process communication (frame/tab process relationship)

IEFRAME.DLL(everything related with the browser user interface)

Windows Layout and display.

Frame rendering for browser applications and content navigation

Control panel functions

Short cuts and Favorites.

Inter-process communication (frame/tab process relationship)

MSHTML.DLL :

(core rendering engine for the browser, does all html interpretation and rendering

MSHTML is in the charge of formatting the web page, creating and maintaining tables, objects, hosting ActiveX controls, drawing image files etc. MSHTML is the host for Internet Explorer applications, MSHTML can even host other applications to view Internet documents.)

Responsible for html and css parsing

Rendering functionality

Tag handler for MSXML/Jscript/Vbscript/ActiveX controls/Java Applet/JVM/Doc

Manage the Document modules

XSS filter

Developer Tools

INETCPL.CPL ( the internet explorer's control panel item )

   

Protected mode:

Protected mode uses the windows vista integrity mechanism to run the internet explorer process at low integrity. The main features of the integrity level mechanism is follows:

Securable objects, such as files and registry keys, have security descriptors that define the integrity level or level of privilege required for write access to the object.

Processes have an integrity level defined in the security access token. In protected Mode, Internet explorer has a low integrity level. Applications run from the start menu have a medium integrity level. Application that require administrator permissions run with a high integrity level.

Low integrity processes cannot gain write access to objects at higher integrity level

Low integrity process cannot gain write access to objects at higher integrity levels, even if the user's SID is granted write access in the discretionary access control. Integrity level checks are performed before user access permission checks/

Low integrity:

Temporary Internet Files folder

The history folder

The Cookies folder

The Favorites folder

The Windows temporary file folders

Enhanced protected mode:

Disable incompatible add-ons.

![[Pasted image 20210818203854.png]]

   

Proxy

Options: WPAD/PAC, Static Proxy

Static Proxy: Proxy would delegate DNS query, can set bypass list

Proxy auto-config:

[https://en.wikipedia.org/wiki/Proxy_auto-config](https://en.wikipedia.org/wiki/Proxy_auto-config)

[https://findproxyforurl.com/](https://findproxyforurl.com/)

Tools for troubleshooting:

[https://joji.blob.core.windows.net/tools/IEIISRescueTools.zip](https://joji.blob.core.windows.net/tools/IEIISRescueTools.zip) (password: msft)

Network Monitor

ETL

WinHttpDiag

WinHTTP Web Proxy Auto-Discovery Service