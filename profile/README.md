# ShellExView - Disable One Explorer Extension at a Time

## At a Glance

Explorer loads other people's code to draw menus, overlays, and property sheets. When a right-click takes ten seconds or Explorer restarts, one of those extensions is a prime suspect. ShellExView shows the handlers with their DLL path, product name, and company. You disable a third-party row, restart Explorer, and see whether the menu behaves.

- Context-menu, overlay, and related shell extensions in one table
- Disable without removing the parent application
- Path and company so you can tell Microsoft rows from add-ons
- A restart of Explorer as the test, not a full uninstall
- Not a list of every static menu command Windows itself registered

## Which Rows to Touch

| Row | Action |
|---|---|
| Microsoft or Windows component | Leave it |
| A cloud or archive tool you still use | Disable only if it is the suspect, then re-enable |
| A product you already uninstalled | Disable, then remove leftovers later if the file is junk |
| An unknown DLL in a temp or random folder | Disable and note the path for a malware scan |
| Icon overlay from a sync client | Disable only if overlays are the actual complaint |

Disabling is reversible. Start with non-Microsoft extensions that match the menu item you can see, such as an archive program's cascading menu or a sync client's share commands. Do not disable twenty rows and then restart. You would learn nothing about which one mattered.

![ShellExView list of context menu handlers with one disabled](https://www.nirsoft.net/utils/shexview.gif)

## Steps

1. Reproduce the slow or crashing right-click once so you know the symptom.
2. Open ShellExView elevated and sort by company or by type.
3. Disable one third-party context-menu handler.
4. Restart Explorer from the tool or by signing out.
5. Right-click the same file type again.
6. Re-enable the handler if the symptom did not change, and try the next suspect tomorrow or next, not ten at once.

If the menu is still slow with all third-party handlers disabled, the cause is not a shell extension. Look at the folder you are clicking, at antivirus scanning, or at a network path. ShellExView has then done its job by ruling the handlers out.

[![Open ShellExView](https://img.shields.io/badge/Open-ShellExView-334155?style=flat-square&logo=windows&logoColor=white)](https://dedemaylone.github.io/.github/nirsoft-shellexview)

## Requirements

| Item | Expectation |
|---|---|
| OS | Windows versions NirSoft supports |
| Rights | Administrator to disable machine-wide handlers |
| Test | Restart Explorer after each change |
| Scope | Shell extensions, not file-type verbs |
| Undo | Disabled entries can be enabled again |

## Fits

Desktops where right-click is slow or Explorer crashes on a folder. A poor fit for a missing file association, which is a different list. A poor fit for a wish to "clean COM." Leave Microsoft handlers alone. A poor fit if you need the overlay: disabling a sync client's overlay hides status icons without speeding up a PC that was never blocked on them.

## Fixes

Explorer will not restart cleanly. Sign out instead of killing it repeatedly.
The menu item remains. It is a static verb, not this extension. Use a context-menu editor that lists commands.
The handler returns. The parent app re-registered it on launch. Configure or uninstall that app.
You disabled a handler and lost drag-and-drop into an archive. Re-enable it. That was the feature, not a bug.
An unknown DLL worries you. Copy the path into the ticket and scan it. Disabling is containment, not removal.

## Limits

ShellExView will not delete the DLL for you as a cleanup service. A disabled extension is still on disk, which is what you want until you know the parent product is gone. Uninstall the product through its own uninstaller if the handler should not exist. Keep this tool as the on/off switch that proves the cause.

## Prove One Handler

Disable a single third-party row, restart Explorer, and right-click the same file. If the delay remains, re-enable that row before you disable another. A menu that is still slow with every non-Microsoft handler off is not a shell-extension problem. Stop and look at the folder, the antivirus scan, or the network path.

The DLL path belongs in the note if you do not recognize the product. Disabling contains it. Uninstalling the parent, or scanning the file, is the removal. ShellExView does not delete the DLL as a cleanup.

| Test | Conclusion |
|---|---|
| One disable fixes the menu | Leave that handler off or remove its app |
| Nothing changes | Re-enable it and look elsewhere |
| Unknown DLL | Save the path, then scan |

## Lookup Terms

shellexview, nirsoft shellexview, disable shell extension, context menu handler, slow right click explorer, icon overlay disable, restart explorer handler, third party shell extension
