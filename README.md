import urllib.request
from pathlib import Path
import webbrowser
import time
from tqdm import tqdm
import requests

chunk_size = 1048576


apps = ('1','2','3','4','5','6','7','8','9')

print('V1.0\n\nWelcome to my first ... I dunno .. app? or script? or whatever. \n\n')
answers = input('Pick the section - اختار القسم\n\n[1].Browser - متصفح\n[2].Games Launcher - لانشرات  \n[3].Messaging - مكالمات \n[4].Drivers - تعاريف\n[5].Compression - برامج ضغط الملفات\n[6].Tweaks (Coming Soon)\n>')

download_dir = Path('Downloads')
download_dir.mkdir(parents=True, exist_ok=True)

for answer in answers:
    
    # Browsers
    if answer in apps[0]:
        browsers = input('[1].Google Chrome\n[2].Firefox\n[3].Brave\n>')
        filename = ('Chrome.exe', 'Firefox Installer.exe', 'BraveBrowserSetup-BRV010.exe' )
        url = ('https://dl.google.com/tag/s/appguid%3D%7B8A69D345-D564-463C-AFF1-A69D9E530F96%7D%26iid%3D%7BE6532B7A-996B-5D7B-DE72-3336C232BEC5%7D%26lang%3Den%26browser%3D4%26usagestats%3D1%26appname%3DGoogle%2520Chrome%26needsadmin%3Dprefers%26ap%3Dx64-stable-statsdef_1%26brand%3DCHBD%26installdataindex%3Dempty/update2/installers/ChromeSetup.exe', 'https://cdn.stubdownloader.services.mozilla.com/builds/firefox-stub/ar/win/3626c7a2b71d5c76e705c6ee09377a11af16a9ef578cafcb9dc0b2f7e36f8a06/Firefox%20Installer.exe', 'https://referrals.brave.com/latest/BraveBrowserSetup-BRV010.exe')
        for browser in browsers:
            if browser in apps[0]:
                try:
                    r = requests.get(url[0], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[0], 'wb') as f:
                        for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                 total = size/chunk_size, unit = 'MB'):
                                                                                  f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')

            if browser in apps[1]:
                try:
                      r = requests.get(url[1], stream=True)

                      size = int(r.headers['content-length'])

                      with open(filename[1], 'wb') as f:
                          for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                   total = size/chunk_size, unit = 'MB'):
                                                                                    f.write(data)
                except:
            
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')

            if browser in apps[2]:
                try:
                    r = requests.get(url[2], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[2], 'wb') as f:
                        for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                 total = size/chunk_size, unit = 'MB'):
                                                                                  f.write(data)
                except:
                        print('\n\n\nError - حدث خطأ في التحميل\n\n\n')
            else:
                print(' ')

    # Games Launchers
    if answer in apps[1]:
        launchers = input('[1].Steam\n[2].Battlenet\n[3].EA\n[4].Epic Games\n>')
        filename = ('SteamSetup.exe', 'Battle.net-Setup.exe' , 'EAappInstaller.exe', 'EpicInstaller-15.7.0.msi')
        url = ('https://cdn.akamai.steamstatic.com/client/installer/SteamSetup.exe', 'https://downloader.battle.net/download/getInstaller?os=win&installer=Battle.net-Setup.exe', 'https://origin-a.akamaihd.net/EA-Desktop-Client-Download/installer-releases/EAappInstaller.exe', 'https://epicgames-download1.akamaized.net/Builds/UnrealEngineLauncher/Installers/Win32/EpicInstaller-15.7.0.msi?launcherfilename=EpicInstaller-15.7.0.msi' )
        for launcher in launchers:
            if launcher in apps[0]:
                try:
                    r = requests.get(url[0], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[0], 'wb') as f:
                        for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                 total = size/chunk_size, unit = 'MB'):
                                                                                  f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')

            if launcher in apps[1]:
                try:
                    r = requests.get(url[1], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[1], 'wb') as f:
                            for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                     total = size/chunk_size, unit = 'MB'):
                                                                                      f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')

            if launcher in apps[2]:
                try:
                    r = requests.get(url[2], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[2], 'wb') as f:
                            for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                     total = size/chunk_size, unit = 'MB'):
                                                                                      f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')

            if launcher in apps[3]:
                try:
                    r = requests.get(url[3], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[3], 'wb') as f:
                        for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                 total = size/chunk_size, unit = 'MB'):
                                                                                  f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')

            else:
                print(' ')

    if answer in apps[2]:
        messagings = input('[1].Discord\n[2].Teamspeak\n[3].Zoom call\n>')
        filename = ('DiscordSetup.exe', 'TeamSpeak3-Client-win64-3.6.1.exe', 'ZoomInstallerFull.exe')
        url = ('https://dl.discordapp.net/distro/app/stable/win/x86/1.0.9018/DiscordSetup.exe', 'https://files.teamspeak-services.com/releases/client/3.6.1/TeamSpeak3-Client-win64-3.6.1.exe', 'https://cdn.zoom.us/prod/5.16.2.22807/x64/ZoomInstallerFull.exe')
        for messaging in messagings:
            if messaging in apps[0]:
                try:
                    r = requests.get(url[0], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[0], 'wb') as f:
                        for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                 total = size/chunk_size, unit = 'MB'):
                                                                                  f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')


            if messaging in apps[1]:
                try:
                    r = requests.get(url[1], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[1], 'wb') as f:
                            for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                     total = size/chunk_size, unit = 'MB'):
                                                                                      f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')


            if messaging in apps[2]:
                try:
                    r = requests.get(url[2], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[2], 'wb') as f:
                        for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                 total = size/chunk_size, unit = 'MB'):
                                                                                  f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')
                                                                                      
            else:
                print(' ')

    # Drivers ( I need to add more drivers like Eathernet/Wifi drivers)
    if answer in apps[3]:
        gpus = input('[1].Nvidia Geforce Experience\n[2].AMD Adrenalin Edition\n>')
        for gpu in gpus:
            if gpu in apps[0]:
                print("للاسف موقع نفيديا مو سامح بالتحميل التلقائي .. لازم تحمل التعريف بشكل يدوي")
                webbrowser.open_new('https://www.nvidia.com/en-me/geforce/geforce-experience/')

            if gpu in apps[1]:
                print("للاسف موقع اي ام دي مو سامح بالتحميل التلقائي .. لازم تحمل التعريف بشكل يدوي")
                webbrowser.open_new('https://www.amd.com/en/support')
            else:
                print(' ')
                

    if answer in apps[4]:
        extractings = input('[1].WinRar\n[2].7zip\n>')
        filename = ('winrar-x64-624.exe', '7z2301-x64.exe')
        url = ('https://www.win-rar.com/fileadmin/winrar-versions/winrar/winrar-x64-624.exe', 'https://www.7-zip.org/a/7z2301-x64.exe')
        for extracting in extractings:
            if extracting in apps[0]:
                try:
                    r = requests.get(url[0], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[0], 'wb') as f:
                        for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                 total = size/chunk_size, unit = 'MB'):
                                                                              f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')                                                              
    
            if extracting in apps[1]:
                try:
                    r = requests.get(url[1], stream=True)

                    size = int(r.headers['content-length'])

                    with open(filename[1], 'wb') as f:
                        for data in tqdm(iterable = r.iter_content(chunk_size = chunk_size),
                                                 total = size/chunk_size, unit = 'MB'):
                                                                                  f.write(data)
                except:
                    print('\n\n\nError - حدث خطأ في التحميل\n\n\n')

            else:
                print(' ')

    
    if answer in apps[5]:
        print()
        print()
        print('Bruh I just told you coming soon')

    #if answer in apps[6]:
        #Benchmark

    #if answer in apps[7]:


print('\n\nIf you have any app that you want me to add to this list feel free to ask me on whatsapp or twitter\n\nاذا عندك اي برنامج حاب اني اضيفه للستة البرامج تشرفني على الواتس اب او على تويتر ')

print('\n\n@_NoName_x1')
print('\n+966 53 191 8161')
print('\n\n\n\n\n\n----------*DONE*----------')
input()
