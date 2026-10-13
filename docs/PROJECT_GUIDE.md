# Chaotic mouse experiments

Cursor-effect experiments in Python/Tkinter plus a browser edition. The Python programs manipulate the operating-system pointer; the HTML version animates elements inside a webpage.

## Browser edition

Open `index.html` or serve the directory with `python3 -m http.server 8000 --bind 127.0.0.1`. Use the control panel to pause effects, toggle chaos/flicker, choose cursor shape, and adjust ghost-cursor count and intensity. External page resources may require internet access.

## Python edition

Use Windows with Python, Tkinter, and PyAutoGUI. The source uses `ctypes.windll.user32` and Windows transparency behavior, so it is not a portable Linux/macOS desktop application.

```powershell
py -m venv .venv
.venv\Scripts\python.exe -m pip install pyautogui
.venv\Scripts\python.exe Final.py
```

`Final.py` contains the main control-panel implementation. `test11.py` is another interactive prototype with trails/flashes, not an automated test. `unpredictable_mouse.py` is a smaller movement loop that handles Ctrl+C and attempts to reset speed. Earlier prototypes use differing Windows constants; do not assume every speed-control implementation works identically.

## Architecture and verification

The Python versions combine movement loops, shared state, and Tkinter cursor windows. `Final.py` exposes Pause All Effects and close handling. Verify those controls in an isolated desktop session before exploring movement settings. Run only one pointer-controlling experiment at a time. There is no dependency lockfile or automated test suite; these programs should not be launched by unattended CI.

## More documentation

- [Source, command, and configuration reference](REFERENCE.md)
- [Contributing](../CONTRIBUTING.md)
