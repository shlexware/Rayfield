# Rayfield Interface Suite
This is the written documentation for Rayfield Interface Suite

Last updated for the Beta 1 release

## Booting the Library
```lua
local Rayfield = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Rayfield/main/source'))()
```



## Creating a Window
```lua
local Window = Rayfield:CreateWindow({Name = "Rayfield Example Window"})
```



## Creating a Tab
```lua
local Tab = Window:CreateTab("Tab Example")
```

## Creating a Section
```lua
local Section = Tab:CreateSection("Section Example")
```

## Notifying the user
```lua
Rayfield:Notify("Title Example","Content/Description Example")
```

## Creating a Button
```lua
Tab:CreateButton({
	Name = "Button Example",
	Callback = function()
		-- The function that takes place when the button is pressed
	end,
})
```


## Creating a Toggle
```lua
Tab:CreateToggle({
	Name = "Toggle Example",
	CurrentValue = false,
	Callback = function(Value)
		-- The function that takes place when the toggle is pressed
    -- The variable (Value) is a boolean on whether the toggle is true or false
	end,
})
```

## Creating a Color Picker
Not in Beta 1


## Creating a Slider
```lua
Tab:CreateSlider({
	Name = "Slider Example",
	Range = {0, 100},
	Increment = 10,
	Suffix = "Bananas",
	CurrentValue = 10,
	Callback = function(Value)
		-- The function that takes place when the slider changes
    -- The variable (Value) is a number which correlates to the value the slider is currently at
	end,
})
```

## Creating a Label
```lua
Tab:CreateLabel("Label Example")
```

## Creating a Paragraph
```lua
Tab:CreateParagraph({Title = "Paragraph Example", Content = "Paragraph Example"})
```


## Creating an Adaptive Input
```lua
Tab:CreateInput({
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
Tab:CreateKeybind({
	Name = "Keybind Example",
	CurrentKeybind = "Q",
	Callback = function(Keybind)
		-- The function that takes place when the keybind is pressed
    -- The variable (Keybind) is a string for the keybind currently in use
	end,
})
```


## Creating a Dropdown menu
```lua
Tab:CreateDropdown({
	Name = "Dropdown Example",
	Options = {"Option 1","Option 2"},
	CurrentOption = "hi",
	Callback = function(Option)
	  -- The function that takes place when the selected option is changed
    -- The variable (Option) is a string for the value that the dropdown was changed to
	end,
})
```

## Destroying the Interface
Not in Beta 1
