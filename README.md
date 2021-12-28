local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/GreenDeno/Venyx-UI-Library/main/source.lua"))()
local venyx = library.new("Ninja Legends", 5013109572)
 
local page = venyx:addPage("Main", 5012544693)
local section2 = page:addSection("Main")
local section2 = page:addSection("Credits SCRIPT NONAME#9999")
local section2 = page:addSection("Credits UI NONAME#9999")
local section2 = page:addSection("DISCORD https://discord.gg/vuZ9AEyv")
local page = venyx:addPage("Auto Fam", 5012544693)
local section1 = page:addSection("Auto Fam")
local section3 = page:addSection("Telepor")
local theme = venyx:addPage("Theme", 5012544693)
local colors = theme:addSection("Colors")
 
 
section1:addToggle("Auto Fam", _G.FastAttack, function(value)
_G.FastAttack = value
end)
 
 
local themes = {
Background = Color3.fromRGB(24, 24, 24),
Glow = Color3.fromRGB(0, 0, 0),
Accent = Color3.fromRGB(10, 10, 10),
LightContrast = Color3.fromRGB(20, 20, 20),
DarkContrast = Color3.fromRGB(14, 14, 14),  
TextColor = Color3.fromRGB(255, 255, 255)
}
 
 
for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
colors:addColorPicker(theme, color, function(color3)
venyx:setTheme(theme, color3)
end)
end
 
-- load
venyx:SelectPage(venyx.pages[1], true)
 
 
 
 
 
spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
        if _G.FastAttack then
            local Combat = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
            local Cemara = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
            Cemara.CameraShakeInstance.CameraShakeState = {FadingIn = 3, FadingOut = 2, Sustained = 0, Inactive = 1}
            Combat.activeController.timeToNextAttack = 0
            Combat.activeController.hitboxMagnitude = 120
            Combat.activeController.increment = 3
        end
    end)
end) 
end)
 
 
spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
        if _G.FastAttack then
            game:GetService'VirtualUser':CaptureController()
            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
        end
    end)
end) 
end)


section2:addKeybind("Toggle KeyBind", Enum.KeyCode.RightControl, function()
print("Activated Keybind")
venyx:toggle()
end, function()
print("Changed Keybind")
end)



section3:addButton("Sell Ninjitsu", function()
game.Players.localPlayer.character.HumanoidRootPart.CFrame = CFrame.new(66.282608, 2.98562837, -48.2522697, 0.268565118, -1.70126864e-08, -0.963261545, 1.98095567e-08, 1, -1.21384804e-08, 0.963261545, -1.58218114e-08, 0.268565118)
print("Clicked")
end)
section3:addButton("SHOP", function()
game.Players.localPlayer.character.HumanoidRootPart.CFrame = CFrame.new(126.05088, 3.22562909, 30.3532524, -0.00145555031, 4.85222671e-08, -0.999998927, -6.52748113e-08, 1, 4.86173306e-08, 0.999998927, 6.53455103e-08, -0.00145555031)
print("Clicked")
end)
section3:addButton("SKILLS", function()
game.Players.localPlayer.character.HumanoidRootPart.CFrame = CFrame.new(92.5971222, 2.98562813, 89.9834366, -0.998935521, 9.74762528e-08, -0.0461289063, 9.83901316e-08, 1, -1.75408754e-08, 0.0461289063, -2.20608314e-08, -0.998935521)
print("Clicked")
end)
