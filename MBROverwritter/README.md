## Hello, i present you this instructions to repair your computer after running the overwriter.
### Read carefully and follow the steps to recover your files succesfully or your data can corrupt too easily! (This includes Windows essential files)
(I tested on Windows 7)

1. You will see this message <blockquote class="imgur-embed-pub" lang="en" data-id="a/dUUHp0P"  ><a href="//imgur.com/a/dUUHp0P">Pic1</a></blockquote>

2. Now, insert your windows installation cd

3. After setting your preferences go to "Repair your computer"

4. Go to the "Recovery Tools"

5. Select "Startup Repair"

6. Wait until the tool repair the startup errors

7. Restart the computer selecting the "Finish" button

8. Now in the message you will see many spaces before "Ooops!...", that is a good signal! <blockquote class="imgur-embed-pub" lang="en" data-id="a/dUUHp0P"  ><a href="//imgur.com/a/dUUHp0P">Pic 2</a></blockquote>

9. Restart the computer and repeat the 3rd and 4th steps

10. If you see "Windows 7" on the OS list select it <blockquote class="imgur-embed-pub" lang="en" data-id="a/dUUHp0P"  ><a href="//imgur.com/a/dUUHp0P">Pic 3</a></blockquote>

11. Use again the "Recovery Tools" and click "Next"

12. Start Command-Prompt

13. Type this commands: bootrec /fixmbr, bootrec /fixboot and bootrec /rebuildbcd <blockquote class="imgur-embed-pub" lang="en" data-id="a/dUUHp0P"  ><a href="//imgur.com/a/dUUHp0P">Pic 4</a></blockquote>

(As you can see, my main drive is E:\, if you can see your main drive go to it and in %TEMP% delete the files to ensure the .bat dont overwrite the mbr again, is allocated on a folder with the name like 4D0E.tmp)

14. Before restart you will make a batch-file with this commands:
```
REG DELETE "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer" /v "NoViewonDrive" /f
REG DELETE "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run" /v "Payload" /f
REG DELETE "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer" /v "NoDrives" /f
schtasks /delete /TN BSODPayload /f
rd %temp% /s /q
REG ADD "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" /v "PromptOnSecureDesktop" /t REG_DWORD /d "0" /f
REG ADD "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" /v "ConsentPromptBehaviorAdmin" /t REG_DWORD /d "0" /f
REG ADD "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" /v "EnableLUA" /t REG_DWORD /d "1" /f
REG DELETE "HKLM\SYSTEM\CurrentControlSet\Control\Keyboard Layout" /v "Scancode Map" /f
REG ADD "HKCU\Control Panel\Mouse" /v SwapMouseButtons /d "0" /f
REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\System" /v "DisableTaskMgr" /f
```
Insert it on a USB stick or into any other removable device

15. Now restart your computer

16. If you see the "Computer" category you cannot see your hdd only the removable device <blockquote class="imgur-embed-pub" lang="en" data-id="a/dUUHp0P"  ><a href="//imgur.com/a/dUUHp0P">Pic 5</a></blockquote>

17. Quickly open the File Explorer and run the batch-file with administrator privileges (Close any other window, ensure you close the windows of powershell)

18. Restart your computer again

When you log on, your drives will be back and your files restored!! <blockquote class="imgur-embed-pub" lang="en" data-id="a/dUUHp0P"  ><a href="//imgur.com/a/dUUHp0P">Pic 6</a></blockquote>
