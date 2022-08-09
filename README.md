# gnome-shell-extension-ideapad
Lenovo IdeaPad goodies for GNOME Shell

*At the moment the extension only provides an easy and user-friendly way to toggle the battery conservation mode available on Levono Ideapad laptops and visually get its current state.*

# Installation
Simply install the extension from the [official GNOME extensions website](https://extensions.gnome.org/extension/2992/ideapad/) (recommended). Alternatively, manually download or clone the repository under `~/.local/share/gnome-shell/extensions/ideapad@laurento.frittella`

In both cases, few additional steps are required. Please check the dedicate following section.

# Usage
The extension adds a new entry *Toggle Conservation Mode* to the panel and shows an icon on the status menu to indicate when the battery conservation mode is enabled.

If your particular laptop model supports it, the conservation mode limits battery charging to 55-60% of its capacity to improve battery life. It is particularly useful when the laptop runs on external power most of the time.

![](screenshot.png)

# Additional Required Settings
* using udev to set the permissions for `/sys/bus/platform/drivers/ideapad_acpi/VPC2004:00/conservation_mode` is still WIP

# Wrong battery estimation displayed
Depending on the kernel version you are running, a minor cosmetic issue might still exist. However, if the permanent "Estimating..." battery status displayed in GNOME bugs you, there is also a solution.

Actually, this issue should be fixed in kernels 5.19+. If you are running an older kernel, you can try applying [the patch here](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=185d20694a8aceb4eda9fc1314cbaad0df0aab07). Thanks to Martino Fontana for pointing this out.

Alternatively, you could use the patch I initially suggested in [this uPower merge request](https://gitlab.freedesktop.org/upower/upower/-/merge_requests/46). However, I would personally advice to go for the kernel patch. It is a much cleaner solution.
