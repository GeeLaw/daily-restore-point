# A restore point a day keeps disasters away

This repository contains necessary files that allows automatic creation of System Restore points every day around 10:30 PM (Beijing time).

## How to use the repository

1. Clone it;
2. Check yourself the content, ensure you understand what the registry file and the Task Scheduler task file will do;
3. Import the registry file;
4. Import the task into Task Schduler (make necessary modifications if you want).

## Nota bene

As this is a repository for Windows users, files in this repository use CR-LF line ending sequence. Do make sure your files are in CR-LF before using them. It is possible that certain Windows programs require the file to be in CR-LF: for example, [the behaviour is undefined if a batch file does not use CR-LF](https://blogs.msdn.microsoft.com/oldnewthing/20170802-00/?p=96735#comment-1305325).

## What does each file do?

The registry file sets the restore point creation frequency limit to one per 0.5 days. Starting with Windows 8, the default limit is one per day if the corresponding value does not exist, which creates issue for daily creation as the task is randomly delayed.

The XML is an exported Task Scheduler task that creates the point with [`Checkpoint-Computer` cmdlet](http://go.microsoft.com/fwlink/?LinkId=821566).
