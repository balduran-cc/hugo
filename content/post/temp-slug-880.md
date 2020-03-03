+++
author = "Balduran Chang"
categories = ["developer", "mac", "python"]
date = 2015-03-23T10:04:31Z
description = ""
draft = false
slug = "temp-slug-880"
tags = ["developer", "mac", "python"]
title = "build python environment on MAC"

+++


1. 用 homebrew 安裝 python

	brew instal python

2. setuptools & pip was installed by homebrew ，但我們需要更新一下  

	pip install –upgrade setuptools  
	pip install –upgrade pip


3. build link in Application folder  
	brew linkapps 
會在application下產生兩個link, IDLE.app and python launcher.app

4. 安裝virtualenv
	pip install virtualenv

5. 使用 virtualenv  
virtualenv first  
source first/bin/activate  
這時就已經啟用了first 這個虛擬環境  
pip install markdown  
會在這個環境內安裝 markdown  
deactivate會退出這個環境

Extra reading: https://github.com/Homebrew/homebrew/wiki/Homebrew-and-Python

