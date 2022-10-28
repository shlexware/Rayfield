# Rayfield Interface Suite
This is the written documentation for Rayfield Interface Suite

Last updated for the Beta 4 release

## Booting the Library
```lua
local Rayfield = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Rayfield/main/source'))()
```

### Secure Mode
If the game you're trying to run Rayfield Interface Suite on, is detecting or crashing when you use Rayfield Interface Suite, try using Secure Mode:
- Place `getgenv().SecureMode = true` above the initial Rayfield loadstring

Rayfield will now use Secure Mode and attempt to reduce detection
- Note: This may cause some elements of the UI to look lower quality or may increase loading times slightly

### Enabling Configuration Saving
- Enable ConfigurationSaving in the CreateWindow function
- Choose an appropiate FileName in the CreateWindow function
- Choose an unique flag identifier for each supported element you create
- Place `Rayfield:LoadConfiguration()` at the bottom of all your code

Rayfield will now automatically save and load your configuration

## Creating a Window
```lua
local Window = Rayfield:CreateWindow({
	Name = "Rayfield Example Window",
	LoadingTitle = "Rayfield Interface Suite",
	LoadingSubtitle = "by Sirius",
	ConfigurationSaving = {
		Enabled = true,
		FileName = "Big Hub"
	},
	KeySystem = false, -- Set this to true to use our key system
	KeySettings = {
		Title = "Sirius Hub",
		Subtitle = "Key System",
		Note = "Join the discord (discord.gg/sirius)",
		Key = "ABCDEF"
	}
})
```

## Creating a Tab
```lua
local Tab = Window:CreateTab("Tab Example")
```

## Creating a Section
```lua
local Section = Tab:CreateSection("Section Example")
```
### Updating a Section
```lua
Section:Set("Section Example")
```

## Notifying the user
```lua
Rayfield:Notify("Title Example","Content/Description Example",10010348543) -- (t,c,image)
```

## Creating a Button
```lua
local Button = Tab:CreateButton({
	Name = "Button Example",
	Callback = function()
		-- The function that takes place when the button is pressed
	end,
})
```
### Updating a Button
```lua
Button:Set("Button Example")
```

## Creating a Toggle
```lua
local Toggle = Tab:CreateToggle({
	Name = "Toggle Example",
	CurrentValue = false,
	Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
	Callback = function(Value)
		-- The function that takes place when the toggle is pressed
    		-- The variable (Value) is a boolean on whether the toggle is true or false
	end,
})
```
### Updating a Toggle
```lua
Toggle:Set(false)
```

## Creating a Color Picker
Not in Beta 4


## Creating a Slider
```lua
local Slider = Tab:CreateSlider({
	Name = "Slider Example",
	Range = {0, 100},
	Increment = 10,
	Suffix = "Bananas",
	CurrentValue = 10,
	Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
	Callback = function(Value)
		-- The function that takes place when the slider changes
    		-- The variable (Value) is a number which correlates to the value the slider is currently at
	end,
})
```
### Updating a Slider
```lua
Slider:Set(10) -- The new slider integer value
```

## Creating a Label
```lua
local Label = Tab:CreateLabel("Label Example")
```
### Updating a Label
```lua
Label:Set("Label Example")
```

## Creating a Paragraph
```lua
local Paragraph = Tab:CreateParagraph({Title = "Paragraph Example", Content = "Paragraph Example"})
```
### Updating a Paragraph
```lua
Paragprah:Set({Title = "Paragraph Example", Content = "Paragraph Example"})
```

## Creating an Adaptive Input (TextBox)
```lua
local Input = Tab:CreateInput({
	Name = "Input Example",
	PlaceholderText = "Input Placeholder",
	RemoveTextAfterFocusLost = false,
	Callback = function(Text)
		-- The function that takes place when the input is changed
    		-- The variable (Text) is a string for the value in the text box
	end,
})
```



## Creating a Keybind
```lua
local Keybind = Tab:CreateKeybind({
	Name = "Keybind Example",
	CurrentKeybind = "Q",
	HoldToInteract = false,
	Flag = "Keybind1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
	Callback = function(Keybind)
		-- The function that takes place when the keybind is pressed
    		-- The variable (Keybind) is a boolean for whether the keybind is being held or not (HoldToInteract needs to be true)
	end,
})
```
### Updating a Keybind
```lua
Keybind:Set("RightCtrl") -- Keybind (string)
```

## Creating a Dropdown menu
```lua
local Dropdown = Tab:CreateDropdown({
	Name = "Dropdown Example",
	Options = {"Option 1","Option 2"},
	CurrentOption = "Option 1",
	Flag = "Dropdown1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
	Callback = function(Option)
	  	  -- The function that takes place when the selected option is changed
    	  -- The variable (Option) is a string for the value that the dropdown was changed to
	end,
})
```
### Updating a Dropdown
```lua
Dropdown:Set("Option 2") -- The new option value
```



## Destroying the Interface
```lua
Rayfield:Destroy()
```
