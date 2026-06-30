---
title: Python Tkinter Hotkeys and System Tray
date: 2024-01-25 21:20:30
tags:
categories:
  - [Python, Snippets]
---

# Global Hotkey
```Python

import tkinter as tk
from SwapMouse import run_powershell
from Operations import open_excel
from global_hotkeys import *

# create main window
root_window = tk.Tk()
root_window.title("Tools")
root_window.geometry("400x500")
label1 = tk.Label(root_window, text=f"status")
label1.place(x=20,y=200)
# construct lambda
swap_mouse_lambda = lambda label: run_powershell.run(label=label)
open_excel_lambda = lambda label: open_excel.run(label=label)
# attach a button and relative label
b_swap_mouse = tk.Button(root_window, text="치ㅁㅇ더", command=lambda : swap_mouse_lambda(label=label1)).place(x=30,y=30)
label2 : tk.Label = tk.Label(root_window, text=f"ctrl + alt + m to swap mouse primary button").place(x=30,y=50)
b_open_excel = tk.Button(root_window, text="Open Excel", command=lambda : open_excel_lambda(label=label1)).place(x=80,y=80)
label2 : tk.Label = tk.Label(root_window, text=f"ctrl + alt + e to open excel").place(x=80,y=100)
# add global hotkey
bindings = [
    [["control", "alt", "m"], None, lambda : swap_mouse_lambda(label=label1)],
    [["control", "alt", "e"], None, lambda : open_excel_lambda(label=label1)]]
register_hotkeys(bindings=bindings)
start_checking_hotkeys()
tk.mainloop()

```
# System Tray icon
https://stackoverflow.com/questions/71715851/how-to-add-icon-in-the-taskbar-when-we-are-using-python-tkinter-framework



System Tray icon
https://www.tutorialspoint.com/how-to-create-a-system-tray-icon-of-a-tkinter-application
