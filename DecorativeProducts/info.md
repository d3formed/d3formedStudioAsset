# Billboard V1
---
- Release date: 13th September 2026
- SHA256: `0B46D06EF4C39AB0DB6FD11E33B17BB4438CDB8A174BCFFBABC6A315545ECEB2`
---

## Please check the hash file when downloaded the file!
> I will not be responsible if the product you downloaded from AliExpress or somewhere is broken 💀
### How to verify the file?
> * **Windows:** Open up **PowerShell* and run: `Get-FileHash "C:\path\to\file.exe" -Algorithm SHA256`. Replace the file path `"C:\path\to\file.exe"` with your file.
> * **Linux:** Open **Terminal** and run `sha256sum filename`. Replace the `filename` with your file.
> * **MacOS:** Open **Terminal** and run `shasum -a 256 /path/to/file`. Replace the `path/to/file` with your file. (i don't use macOS, don't ask me where Terminal is 💀)
---
# Instructions
> - **Step 1:** Drag & drop the file (`.rbxm`) to Roblox Studio.
> - **Step 2:** Grab the models (`Design1`, `Design2`, `Design3`, `Design4`) from the `Put in Workspace` folder to any path you want (`Workspace` for example).
> - **Step 3:** Move `data_config` from the "Put in ServerStorage" folder into Roblox Studio's `ServerStorage`.
> - **Step 4:** Configure the `Queue` and `Config`


# Definitions
### This is how the `Config` ModuleScript lists and what do they mean:
```luau
local conf = {
	AnimType = "Slide", -- Animation type (Supported: None, Fade, Slide)
	Duration = 5, -- Duration of an ad can display
	AnimDuration = 2, -- Duration of a transitioning ads
	RandomMode = false -- Randomize the ads
}

return conf
```

- `AnimType`: This is how the billboard transitioning from one to another image, currently supported ones are **None, Fade, and Slide**
- `Duration`: This is how long the billboard can display, for example `5`. It means that the billboards will be shown for 5 seconds then it will transition into another images.
- `AnimDuration`: This is how long can the transition do, such as `Image1` will transitioning to `Image2` for 2 seconds for example. *(Does not apply to None)*
- `RandomMode`: This is a feature where you can make it randomize the next ads when you set it to `true`. if it set to `false` then it will follow the queue like 1 -> 2 -> 3 -> 4 -> etc.. .
---
### Same goes for `Queue` ModuleScript:
```luau
local BillboardQueue = {
	"rbxassetid://128228250021301",
	"rbxassetid://128432869115264",
	"rbxassetid://129061470413977",
	"rbxassetid://71924200708016"
}

return BillboardQueue

-- You can add or change one of the images in 
-- the queue by editing the table above.
```
- `"rbxassetid://XXXXXXXXXXX"`: This is where you put your imageID in. Including `rbxassetid://` prefix with your ImageID is recommended.
- To add more, put a `,` next to it, make a new line and add your `rbxassetid://` with ImageID in.

# Animations
> There are currently 3 animations for the transition of a billboard.
> - **None:** It just show the next image straightfoward. No animation. Nothing. Just constant.
> - **Fade:** It will fade out the current image, then fade in the next image.
> - **Slide:** Think of how you pull a toilet paper, ez.
# Troubleshoot
  - `Error reading data!`: You either forgot to put `,` next to your ImageID when adding another list, bad ImageID, or the list is empty. Re-check your ModuleScript if something is wrong.
  - `Error reading config!`: Check if you have a mistypo, the config is empty (` ` or `nil`), or you have put the number that is below 1 into the `Config`.
