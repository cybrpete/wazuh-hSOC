# Atomic Red Team Setup #
Runs PowerShell with a bypassed execution policy to then load our script and Install Atomic Red Team + Download the Atomics (Tests).
``` powershell
powershell -ep bypass -nop
IEX (IWR 'https://raw.githubusercontent.com/redcanaryco/invoke-atomicredteam/master/install-atomicredteam.ps1' -UseBasicParsing);
Install-AtomicRedTeam -getAtomics
```
### Invoking our first test T1059.001, test 1 ###
``` powershell
Invoke-AtomicTest T1059.001-1
```
# A few other tests to try on your own #
### T1059.001, test 2 (https://atomicredteam.io/execution/T1059.001/) ###
``` powershell
Invoke-AtomicTest T1059.001-2
```
### Software Discovery (https://atomicredteam.io/discovery/T1518.001/) ###
``` powershell
Invoke-AtomicTest T1518
```
### Clipboard Data Attacks (https://atomicredteam.io/collection/T1115/) ###
``` powershell
Invoke-AtomicTest T1115
```
***If you have closed your PowerShell window, you'll have to import the re-import the Invoke-AtomicTest module with this command.***
``` powershell
Import-Module "C:\AtomicRedTeam\invoke-atomicredteam\Invoke-AtomicRedTeam.psd1" -Force
```
