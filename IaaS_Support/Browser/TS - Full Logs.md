# Everything you need is here
   

Please follow the action plan to capture both working and non-working traces. Thanks in advance.

Action Plan

==========

1.  Download IEDigest(iedigest_NET2_195.exe) from: [https://www.microsoft.com/en-us/download/details.aspx?id=51694]
2.  Download(Need to install) Fiddler from [http://www.fiddler2.com/fiddler2/](https://nam06.safelinks.protection.outlook.com/?url=http%3A%2F%2Fwww.fiddler2.com%2Ffiddler2%2F&data=02%7C01%7CJunCheng.Zhu%40microsoft.com%7Ce794723ad1244233777608d8635dfde3%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637368602625916338&sdata=LDagvB1%2FHwY96uPZ%2FZ4ND%2Fm43JYStaTNBmR3OIOwhEQ%3D&reserved=0)
3.  Download Process Monitor from [https://technet.microsoft.com/en-us/sysinternals/processmonitor.aspx](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Furldefense.proofpoint.com%2Fv2%2Furl%3Fu%3Dhttps-3A__nam06.safelinks.protection.outlook.com_-3Furl-3Dhttps-253A-252F-252Ftechnet.microsoft.com-252Fen-2Dus-252Fsysinternals-252Fprocessmonitor.aspx-26data-3D02-257C01-257Cbichuan-2540microsoft.com-257Ca5a9bac7451149fff62d08d696675997-257C72f988bf86f141af91ab2d7cd011db47-257C1-257C0-257C636861768037518033-26sdata-3Dvowmy15IsR9DqR5lwlpE36KX1iAxIryNPHYNUDamBMs-253D-26reserved-3D0%26d%3DDwMGaQ%26c%3DCFXY-ic-VSvSGEXg4f3Olw%26r%3D5nXA_qky4ZseV-DKQ2JxM1REyT0_OjgITEoBY7-bxBo%26m%3D8NAtL31AZtT2dETLEdOAV0nCg3HlQ0ctin9Y_2fsJJk%26s%3DF7pTep03xHx_85Q9QUWg6ExHsjU4hwd6VVnLU6rg4Ag%26e%3D&data=02%7C01%7CJunCheng.Zhu%40microsoft.com%7Ce794723ad1244233777608d8635dfde3%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637368602625916338&sdata=W2gCN%2F90dj2VDwYaHNxXGRGvKtg%2B8SVFg93M6DOYBzM%3D&reserved=0)
4.  Download ie-etw-traces.zip from [http://bianchuan.azurewebsites.net/ie-etw-traces.zip](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Furldefense.proofpoint.com%2Fv2%2Furl%3Fu%3Dhttps-3A__nam06.safelinks.protection.outlook.com_-3Furl-3Dhttp-253A-252F-252Fbianchuan.azurewebsites.net-252Fie-2Detw-2Dtraces.zip-26data-3D02-257C01-257Cbichuan-2540microsoft.com-257Ca5a9bac7451149fff62d08d696675997-257C72f988bf86f141af91ab2d7cd011db47-257C1-257C0-257C636861768037528029-26sdata-3DKZhcH0YoOz5ZFDgkelDqayH9Y8nk0bSA3jYL-252BLy-252F0Tk-253D-26reserved-3D0%26d%3DDwMGaQ%26c%3DCFXY-ic-VSvSGEXg4f3Olw%26r%3D5nXA_qky4ZseV-DKQ2JxM1REyT0_OjgITEoBY7-bxBo%26m%3D8NAtL31AZtT2dETLEdOAV0nCg3HlQ0ctin9Y_2fsJJk%26s%3Dv6FiH55q3vA3KSJBr2ueDgLVRRSfkNNDP60BmPKzVKU%26e%3D&data=02%7C01%7CJunCheng.Zhu%40microsoft.com%7Ce794723ad1244233777608d8635dfde3%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637368602625926333&sdata=nvIfRC1m2MhhlGlM1NW60nW2Wi4wjr80HrvJ08GNq%2BI%3D&reserved=0) to the client.
5.  Download IEZoneAnalyzer from [https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/telligent.evolution.components.attachments/01/5808/00/00/03/45/50/87/IEZoneAnalyzer.3.5.0.5.zip](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Furldefense.proofpoint.com%2Fv2%2Furl%3Fu%3Dhttps-3A__nam06.safelinks.protection.outlook.com_-3Furl-3Dhttps-253A-252F-252Fmsdnshared.blob.core.windows.net-252Fmedia-252FTNBlogsFS-252Fprod.evol.blogs.technet.com-252Ftelligent.evolution.components.attachments-252F01-252F5808-252F00-252F00-252F03-252F45-252F50-252F87-252FIEZoneAnalyzer.3.5.0.5.zip-26data-3D02-257C01-257Cbichuan-2540microsoft.com-257Ca5a9bac7451149fff62d08d696675997-257C72f988bf86f141af91ab2d7cd011db47-257C1-257C0-257C636861768037528029-26sdata-3D7vVH-252FlS0N2JefsUkPeU7BeUHzFtnz3Aj4NsBOWoJVkA-253D-26reserved-3D0%26d%3DDwMGaQ%26c%3DCFXY-ic-VSvSGEXg4f3Olw%26r%3D5nXA_qky4ZseV-DKQ2JxM1REyT0_OjgITEoBY7-bxBo%26m%3D8NAtL31AZtT2dETLEdOAV0nCg3HlQ0ctin9Y_2fsJJk%26s%3DKLzyk6cYYghQrBN7c8YO4J2epb2UOblxJ5cJk-kCf0E%26e%3D&data=02%7C01%7CJunCheng.Zhu%40microsoft.com%7Ce794723ad1244233777608d8635dfde3%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637368602625926333&sdata=Wr8CQQWb%2Bg27KkqtqSvnstvp%2BH4dvlIXAlbVmYEWvf8%3D&reserved=0)

Steps  -

You can create a folder and put all the logs into this folder, compress the folder and upload to the workspace.

Open IE -> Click on “Ctrl+Shift+Delete” to clear all the cache of IE11. Close all browsers.

Double click IEDigest.exe, click Create Report button, it will create a folder called: “IEDigest” on your desktop. Please help compress the folder and upload to workspace.

Open IEZoneAnalyzer , click on  > Zone Map Viewer > Export > to CSV. Please upload the CSV file to the workspace.

  

Open CMD as administrator and run the command “gpresult /h result.html”. Please help upload the HTML to the workspace.

   

Open the application “Procmon.exe”(Please run as administrator).

Decompress the file “ie-etw-traces.zip” Run Command Prompt as administrator -> Cd to the folder “ie-etw-traces”. Run command start.bat, please wait until you see the message “Press any key to continue”. Please don’t press any key on this CMD window and keep the CMD window open.

   

Start Fiddler.

On Fiddler Click Tools -> "Clear WinINET Cache".

On Fiddler Click Tools -> "Clear WinINET Cookies".

On Fiddler Click Tools -> "Fiddler Options", on HTTPS tab, check “Capture HTTPS CONNECTS” and “Decrypt HTTPS traffic” and click OK button. Please click OK button if you get any prompts.

On Fiddler Click "Browse" on the panel to start IE, a blank page will be opened in IE.

Reproduce the issue. Please take a screenshot and upload to the workspace.

On Fiddler Click File | Save | All Sessions to .SAZ file. And upload to workspace

Get back to the Command Prompt for ie-etw-traces. Press “Enter” button to generate the logs. Please compress the folder “ie-etw-traces” and upload to the workspace.

Please go back to the Procmon.exe and select file tab and click the option “Save” -> All events -> OK to save the log file(.PML file). Please upload the file to workspace.