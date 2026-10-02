# Hotkey Utility user guide

Create keyboard and mouse shortcuts for everyday tasks on Windows 10/11 x64. Combine actions into sequences, assign separate actions to a short press and a hold, and switch between keyboard layouts.

Available languages: English, Ukrainian, Georgian, Catalan, Spanish, French and German.

[Back to the product overview](../README.md)

## Getting started

Run **HotkeyUtility.exe**. On first launch, choose a permanent installation folder and select **Install and open**. The default is `C:\Program Files\HotkeyUtility`; Windows may ask for permission to create it. The program creates its settings automatically and runs from the chosen folder.

Settings are stored in `config.xml` beside the program. To move the application with its settings, copy the entire folder. A backup of the previous settings is kept in `config.xml.bak`.

Closing the main window sends the program to the notification area. Use its tray menu to reopen it, pause shortcuts, enable **Start with Windows**, or exit.

## Creating a shortcut

1. Click **+**, enter a name, and use **Record** to capture a key, mouse button or combination. Esc cancels recording.
2. Add actions from the colored library. A click adds to **On press**; a long mouse click adds to **On hold**. You can also drag an action into either sequence or choose the destination with a right-click.
3. Set the action parameters and save the shortcut.

Drag existing actions to reorder them or move them between sequences. Each action has its own enable switch. Double-click an action to edit it; Delete removes the selected action, Space enables or disables it, and Alt+Up/Down changes its position. The hold panel switch enables or disables the whole hold sequence.

Without hold actions, a shortcut runs when pressed. With hold actions, a short press runs its sequence on release; holding the trigger runs the hold sequence once. The default hold threshold is 500 ms. Holding a key does not repeatedly run its actions.

**Keep original function** lets the trigger continue to work normally in the active application. Turn it off to use that key or combination only for the shortcut. Blocking a standalone modifier such as Ctrl can also affect other combinations using it.

## Actions

- **Open URL** opens a website in the default browser.
- **Run program** launches an application. **Advanced** contains arguments and a working folder; leaving the working folder empty uses the selected program’s folder. Paths can use environment variables, for example `%windir%\system32\mspaint.exe`.
- **Open or activate program**, a mode of Run program, activates an existing matching window or launches the application if none exists. By default, the first matching window is used. **Advanced → Target window** provides additional filters and oldest/newest process selection. If Windows refuses the switch, release the shortcut keys to let the program retry. A failed switch leaves other shortcuts active.
- **Key press** sends a key or combination to the active window. Characters depend on that window’s keyboard layout.
- **Mouse click** uses screen coordinates or coordinates relative to a selected window’s inner area. Window-relative points remain valid when the window moves. **Pick position** captures a point; **Show point** highlights it without clicking.
- **Delay** waits before continuing. Add a delay after launching an application if its window needs time to open.
- **Insert text** enters a saved text, signature or multiline template into the active application without changing the clipboard.
- **Keyboard layout** selects a specific installed layout or the previous layout.

Key presses, mouse clicks and text insertion wait for the relevant physical keys or modifiers to be released. Sequences run in order, one at a time.

## Previous keyboard layout

Choose **Use previous keyboard layout**, the first item in the Keyboard layout action’s list.

- With a single-key trigger, each press switches between the current and previous layouts.
- With a combination such as **Win+Space**, keep Win held and press Space again to reach older layouts. Each separate press applies the next layout immediately.
- Release the modifiers to finish. The final selection becomes the most recently used layout; holding Space does not cycle automatically.

History is shared across applications and lasts until Hotkey Utility exits. Manual layout changes are remembered too. Before history is available, the program uses Windows’ loaded-layout order starting after the current layout. With only one layout, the action does nothing.

Shortcuts using this action automatically block the original combination to avoid a second switch by Windows. Put the action under **On press** for the usual repeated-tap behavior.

## Finding and organizing shortcuts

The search field matches names, combinations, websites, programs and action text. While the main window is active, holding Ctrl, Alt, Shift or Win also filters shortcuts using those modifiers; additional keys narrow the results.

**Options → Compact mode** shows more shortcuts at once. Click a card or its arrow to expand the full sequence. Card controls let you edit, duplicate, delete or enable a shortcut. Duplicates start disabled.

**Options → Language** changes the interface language. The initial language is chosen from your installed keyboard layouts.

## Pause and recovery

Use the pause button or tray menu to pause and resume shortcuts. **Ctrl+Alt+Backspace** immediately stops running and queued actions and pauses the program. Actions already completed are not undone.

Shortcuts do not run inside Hotkey Utility’s own windows. An action error ends only that run and skips its remaining steps. Other queued runs and new shortcuts continue to work; no Resume is needed. The error remains visible at the bottom of the main window. Use the details icon to view the report or the copy icon to copy it. **Help → Error details** and the tray menu offer the same report. It includes the shortcut, action, time, version, program paths and window diagnostics; details are copied only when you choose to do so. After locking the computer or resuming from sleep, resume shortcuts explicitly.

If the settings file cannot be read, the program offers to restore its backup. To start paused for recovery, launch `HotkeyUtility.exe --safe`. The `--tray` option starts the program in the notification area.

Applications running with administrator privileges and some Windows-reserved shortcuts may restrict automation.

## Updates

**Options → Auto Update** is enabled by default. The program checks for updates at startup and every 30 minutes, downloads the available version and restarts automatically. Settings are retained. Close any open editor to let installation proceed.

You can disable automatic updates in the same menu. Before manually returning to an older version, keep a separate copy of your settings: older versions may not support the current settings format.

## Contact

[Contact the author](https://www.zuzlan.name/#contact), also available through **Help → Contacts**.
