# Plaguecheat.cc Roblox UI Library

A full-featured Roblox UI library with multiple windows, sections, and interactive components like buttons, toggles, sliders, keybinds, textboxes, dropdowns, color pickers, and a dynamic watermark.

---

## Installation

```lua
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/oShyyyyy/Plaguecheat.cc-Roblox-Ui-library/main/Source.lua", true))()
```

---

## Creating Windows

```lua
local Legit = library:AddWindow('Legit')
local Rage = library:AddWindow('Rage')
local AntiAim = library:AddWindow('Anti-Aim')
```

---

## Adding Sections

```lua
local e = Legit:AddSection('All Features')
```

---

## Components

### Labels
```lua
e:AddLabel('Template Label') 
```

### Buttons
```lua
e:AddButton('Test Button', false, nil, function() 
  print('a') 
end)
```

### Toggles
```lua
e:AddToggle('Testing Toggle', true, Enum.KeyCode.LeftControl, function(v) 
    print(v)
end)

e:AddToggle('Testing Toggle', true, nil, function(v)
    print(v)
end)
```

### Sliders
```lua
e:AddSlider('Template Slider', 100, 10, 50,function(c) 
end)
```

### Keybinds
```lua
local visible = true
e:AddKeyBind('Template Keybind', Enum.KeyCode.Y, function() 
    if watermark:Visible() then
        watermark:Visible(false) 
        visible = not visible
    else
        watermark:Visible(true) 
        visible = not visible
    end
end)
```

### Color Picker
```lua
e:AddColorPallete('Testing Color Pallete', Color3.fromRGB(89, 125, 255), function(a) 
  print(a)
end)
```

### Textboxes
```lua
e:AddTextBox('No filter', nil, false, 5, function(a) print(a) end)
e:AddTextBox('Only numbers', nil, false, 1, function(a) print(a) end)
e:AddTextBox('No special chars', nil, false, 2, function(a) print(a) end)
e:AddTextBox('Only nums+chars', nil, false, 3, function(a) print(a) end)
e:AddTextBox('Only Chars', nil, false, 4, function(a) print(a) end)
```

### Separator
```lua
e:AddSeparateBar()
```

### Dropdowns
```lua
e:AddDropdown('Testing Dropdown', {'opt1','opt2','opt3'}, 'opt2', function(a) print(a) end)
```

---

## Watermark

```lua
local watermark = library:AddWatermark('')
watermark:Visible(true)

-- Auto-update watermark text
local te = watermark
te:UpdateValue(true)
local ms = library.ms or 'hehe wha'

spawn(function()
    while wait(1) do
        local fps = library.fps
        local t = ''
        if #fps < 2 then
            t = 'FPS: '..'0'..fps..' | MS: '..ms
        else
            t = 'FPS: '..fps..' | MS: '..ms
        end
        watermark:ChangeText('i love femboy bro pls I NEED MONEY TO MAKE MY NEW UI TO GET SCRIPT PLEASE GIVE MONEY GUYS '..t)
    end
end)
```

---

## Full Example

```lua
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/oShyyyyy/Plaguecheat.cc-Roblox-Ui-library/main/Source.lua", true))()

local Legit = library:AddWindow('Legit')
local Rage = library:AddWindow('Rage')
local AntiAim = library:AddWindow('Anti-Aim')
local watermark = library:AddWatermark('')

local e = Legit:AddSection('All Features')

e:AddLabel('Template Label') 
e:AddButton('Test Button', false, nil, function() print('a') end)
e:AddToggle('Testing Toggle', true, Enum.KeyCode.LeftControl ,function(v) print(v) end)
e:AddToggle('Testing Toggle', true, nil, function(v) print(v) end)
e:AddSlider('Template Slider', 100, 10, 50,function(c) end)

local visible = true
e:AddKeyBind('Template Keybind', Enum.KeyCode.Y, function() 
    if watermark:Visible() then
        watermark:Visible(false) 
        visible = not visible
    else
        watermark:Visible(true) 
        visible = not visible
    end
end)

e:AddColorPallete('Testing Color Pallete', Color3.fromRGB(89, 125, 255), function(a) print(a) end)
e:AddTextBox('No filter', nil, false, 5, function(a) print(a) end)
e:AddTextBox('Only numbers', nil, false, 1, function(a) print(a) end)
e:AddTextBox('No special chars', nil, false, 2, function(a) print(a) end)
e:AddTextBox('Only nums+chars', nil, false, 3, function(a) print(a) end)
e:AddTextBox('Only Chars', nil, false, 4, function(a) print(a) end)
e:AddSeparateBar()
e:AddDropdown('Testing Dropdown', {'opt1','opt2','opt3'}, 'opt2', function(a) print(a) end)

```

---

## License

This library is provided as-is. Use at your own risk.
