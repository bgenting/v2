# v2
Kings
不定时更新中......

@Echo off
cd /d %~dp0
if exist 英雄联盟卸载.exe (goto next) else (goto baddir)
:next
@echo off
echo.
echo =======================================
echo 正在为批处理文件提升超级管理员权限。。。
echo =======================================
cd /d %~dp0
%1 start "" mshta vbscript:createobject("shell.Application").shellexecute("""%~0""","::",,"runas",1)(window.close)&exit

@echo off
color 3E
echo %username% 已获取超级管理员权限
echo.
title LOL禁用or恢复全家桶批处理工具（2022.01.16）
echo 【功能说明】
echo 禁用不知道什么插件
echo.
echo 【特别提醒】
echo 1.使用前请【确保】已经关闭LOL和WeGame
echo 2.更新游戏时：需要先恢复全家桶待更新完再禁用，否则会显示文件被占用；
echo   本批处理脚本无毒，使用的命令都是系统指令
echo.

echo 【注意：脚本即将强制关闭LOL，按任意键将执行！】
pause
taskkill /im CrossProxy.exe /T /F
taskkill /im TPHelper.exe /T /F
taskkill /im GameLoader.exe /T /F
taskkill /im LeagueClient.exe /T /F
taskkill /im tgp_gamead.exe /T /F
taskkill /im TQMCenter.exe /T /F
taskkill /im ACE-Helper.exe /T /F
taskkill /im SGuard64.exe /T /F
taskkill /im SGuardSvc64.exe /T /F
echo.

:on
cd /d %~dp0
choice /c 123 /m "请输入编号：(1)禁用全家桶；(2)恢复全家桶；(3)退出；"
if %errorlevel%==3 goto end
if %errorlevel%==2 goto restore
if %errorlevel%==1 goto disable

:disable
echo 禁用全家桶
rem sc delete "AntiCheatExpert Service"
rem sc delete ACE-GAME
rem sc delete ACE-BASE
rem rmdir /s/q "C:\Program Files\AntiCheatExpert"
rem icacls "C:\Program Files\AntiCheatExpert\SGuard\x64\SGuard64.exe" /deny Everyone:F
rem icacls "C:\Program Files\AntiCheatExpert\SGuard\x64\SGuardSvc64.exe" /deny Everyone:F
rem icacls "C:\Program Files\AntiCheatExpert\SGuard\x64\SGuardUpdate64.exe" /deny Everyone:F
rem icacls "C:\Program Files\AntiCheatExpert" /deny Everyone:(RX,W,F)
icacls Game\TP3Helper.exe /deny Everyone:F
icacls LeagueClient\GameLoader.exe /deny Everyone:F
icacls LeagueClient\TP3Helper.exe /deny Everyone:F
icacls TCLS\Tenio\TenioDL\Tencentdl.exe /deny Everyone:F
icacls TCLS\Tenio\TenioDL\TenioDL.exe /deny Everyone:F
icacls TCLS\Tenio\TenioDL\TenioDL_core.dll /deny Everyone:F
icacls TCLS\TenProtect\Ten\Ten.exe /deny Everyone:F
icacls TCLS\TenProtect\TP\TPHelper\TPHelper.exe /deny Everyone:F
icacls TCLS\TenProtect\TP\TPHelper\TPWeb.exe /deny Everyone:F
icacls TCLS\TenProtect\TP\TPHelper.Installer.exe /deny Everyone:F
icacls TCLS\TenProtect\TenSafe.exe /deny Everyone:F
icacls TCLS\TenProtect\TenSafe_1.exe /deny Everyone:F
icacls TCLS\TenProtect\TP\TPApp.dll /deny Everyone:F
icacls TCLS\AdvertDialog.exe /deny Everyone:F
icacls TCLS\AdvertTips.exe /deny Everyone:F
icacls TCLS\BackgroundDownloader.exe /deny Everyone:F
icacls TCLS\TPSvc.exe /deny Everyone:F
icacls TCLS\TP3Helper.exe /deny Everyone:F
icacls Cross\Core\Stable\CrossProxy.exe /deny Everyone:F
icacls Cross\Apps\AssistInGame\AssistInGame.dll /deny Everyone:F
icacls Cross\Apps\LCULQT\LQT.dll /deny Everyone:F
icacls Cross\Apps\LCULQT\Res.vfs /deny Everyone:F
icacls Cross\Apps\LCULQT\GameDataPlatformClient.dll /deny Everyone:F
icacls Cross\Apps\LCULQT\DataReport.dll /deny Everyone:F
icacls Cross\Apps\LQT\LQT.dll /deny Everyone:F
icacls Cross\Apps\LQTInGame\LQTInGame.dll /deny Everyone:F
icacls Cross\Apps\Trial\LOLApp.dll /deny Everyone:F
icacls Cross\Apps\Trial\GameDataPlatformClient.dll /deny Everyone:F
icacls Cross\Apps\Trial2\LOLApp2.dll /deny Everyone:F
icacls Cross\Apps\Trial2\GameDataPlatformClient.dll /deny Everyone:F
icacls Cross\Apps\Trial2\ACE-GDPClient32.dll /deny Everyone:F
icacls Cross\Apps\Trial2\ACE-GDPOpenProtocol32.tdr /deny Everyone:F
icacls LeagueClient\FeedBack\FeedBack.exe /deny Everyone:F
icacls LeagueClient\FeedBack\ACE-GDPClient32.dll /deny Everyone:F
icacls LeagueClient\FeedBack\ACE-GDPOpenProtocol32.tdr /deny Everyone:F
icacls LeagueClient\FeedBack\BugTrace.dll /deny Everyone:F
icacls LeagueClient\FeedBack\LOLDataApp.dll /deny Everyone:F
icacls LeagueClient\FeedBack\SSOCommon.dll /deny Everyone:F
icacls LeagueClient\FeedBack\SSOPlatform.dll /deny Everyone:F
icacls LeagueClient\NetworkAssist\QM\ProxyAccDownload.exe /deny Everyone:F
icacls LeagueClient\NetworkAssist\QM\QMLolAssist.exe /deny Everyone:F
icacls LeagueClient\NetworkAssist\xunyou\yxqxunyou.exe /deny Everyone:F
icacls LeagueClient\TQM\TQMCenter.exe /deny Everyone:F
icacls LeagueClient\ACE-Helper.exe /deny Everyone:F
rem icacls "C:\Program Files (x86)\Tencent\TGuard" /reset
rem del /f /s /q "C:\Program Files (x86)\Tencent\TGuard\*.dll"
rem icacls "C:\Program Files (x86)\Tencent\TGuard\TGuard.exe" /deny Everyone:F
rem icacls "C:\Program Files (x86)\Tencent\TGuard\TP3Helper.exe" /deny Everyone:F
rem icacls "C:\Program Files (x86)\Tencent\TGuard\TGuardSvc.exe" /deny Everyone:F
rem icacls "C:\Program Files (x86)\Tencent\TGuard\Update.exe" /deny Everyone:F
rem icacls "C:\Program Files (x86)\Tencent\TGuard\TenSRL.dat" /deny Everyone:F
rem icacls "C:\Program Files (x86)\Tencent\TGuard" /deny Everyone:F
rem del /f /s /q "%userprofile%\AppData\LocalLow\DNF\*.trc"
goto on

:restore
echo 恢复全家桶
icacls Game\TP3Helper.exe /reset
icacls LeagueClient\GameLoader.exe /reset
icacls LeagueClient\TP3Helper.exe /reset
icacls TCLS\TenProtect\TP\TPHelper\TPHelper.exe /reset
icacls TCLS\TenProtect\TP\TPHelper\TPWeb.exe /reset
icacls TCLS\BackgroundDownloader.exe /reset
icacls TCLS\TPSvc.exe /reset
icacls TCLS\TenProtect\TenSafe.exe /reset
icacls TCLS\TenProtect\TenSafe_1.exe /reset
icacls TCLS\TenProtect\TP\TPApp.dll /reset
icacls Cross\Core\Stable\CrossProxy.exe /reset
icacls Cross\Apps\AssistInGame\AssistInGame.dll /reset
icacls Cross\Apps\LCULQT\LQT.dll /reset
icacls Cross\Apps\LCULQT\Res.vfs /reset
icacls Cross\Apps\LCULQT\GameDataPlatformClient.dll /reset
icacls Cross\Apps\LCULQT\DataReport.dll /reset
icacls Cross\Apps\LQT\LQT.dll /reset
icacls Cross\Apps\LQTInGame\LQTInGame.dll /reset
icacls Cross\Apps\LQTInGame\res.vfs /reset
icacls Cross\Apps\Trial\LOLApp.dll /reset
icacls Cross\Apps\Trial\res.vfs /reset
icacls Cross\Apps\Trial\GameDataPlatformClient.dll /reset
icacls Cross\Apps\Trial2\LOLApp2.dll /reset
icacls Cross\Apps\Trial2\res.vfs /reset
icacls Cross\Apps\Trial2\GameDataPlatformClient.dll /reset
icacls Cross\Apps\Trial2\ACE-GDPClient32.dll /reset
icacls Cross\Apps\Trial2\ACE-GDPOpenProtocol32.tdr /reset
icacls LeagueClient\FeedBack\FeedBack.exe /reset
icacls LeagueClient\FeedBack\ACE-GDPClient32.dll /reset
icacls LeagueClient\FeedBack\ACE-GDPOpenProtocol32.tdr /reset
icacls LeagueClient\FeedBack\BugTrace.dll /reset
icacls LeagueClient\FeedBack\LOLDataApp.dll /reset
icacls LeagueClient\FeedBack\SSOCommon.dll /reset
icacls LeagueClient\FeedBack\SSOPlatform.dll /reset
icacls LeagueClient\NetworkAssist\QM\ProxyAccDownload.exe /reset
icacls LeagueClient\NetworkAssist\QM\QMLolAssist.exe /reset
icacls LeagueClient\NetworkAssist\xunyou\yxqxunyou.exe /reset
icacls LeagueClient\TQM\TQMCenter.exe /reset
icacls TCLS\Tenio\TenioDL\Tencentdl.exe /reset
icacls TCLS\Tenio\TenioDL\TenioDL.exe /reset
icacls TCLS\Tenio\TenioDL\TenioDL_core.dll /reset
icacls TCLS\TenProtect\Ten\Ten.exe /reset
icacls TCLS\TenProtect\TP\TPHelper\TPHelper.Installer.exe /reset
icacls TCLS\TP3Helper.exe /reset
rem icacls "C:\Program Files (x86)\Tencent\TGuard" /reset
rem icacls "C:\Program Files (x86)\Tencent\TGuard\TGuard.exe" /reset
rem icacls "C:\Program Files (x86)\Tencent\TGuard\TP3Helper.exe" /reset
rem icacls "C:\Program Files (x86)\Tencent\TGuard\TGuardSvc.exe" /reset
rem icacls "C:\Program Files (x86)\Tencent\TGuard\Update.exe" /reset
rem icacls "C:\Program Files (x86)\Tencent\TGuard\TenSRL.dat" /reset
rem icacls "C:\Program Files\AntiCheatExpert\SGuard\x64\SGuard64.exe" /reset
rem icacls "C:\Program Files\AntiCheatExpert\SGuard\x64\SGuardSvc64.exe" /reset
rem icacls "C:\Program Files\AntiCheatExpert\SGuard\x64\SGuardUpdate64.exe" /reset
rem icacls "C:\Program Files\AntiCheatExpert\" /reset
icacls LeagueClient\ACE-Helper.exe /reset
goto on

:baddir
echo.
echo 首次运行本脚本，请把本脚本放在[英雄联盟]根目录下
echo （例：若游戏安装目录为【D：\英雄联盟】，则将该工具箱放在【D：\英雄联盟】目录下后再执行。）
echo.
pause
echo 退出脚本
exit

:end
echo 退出脚本
exit
