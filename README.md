local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
 
OrionLib:MakeNotification({
	Name = "Script Executed",
	Content = "cool its executed",
	Image = "rbxassetid://4483345998",
	Time = 5
})
 
 
local Window = OrionLib:MakeWindow({Name = "AdminLib", HidePremium = false, SaveConfig = true, ConfigFolder = "OrionTest"})
 
local Tab = Window:MakeTab({
	Name = "Main.",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
local Section = Tab:AddSection({
	Name = "Main"
})
 
Tab:AddButton({
	Name = "Speed!",
	Callback = function()
      		game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 120
  	end    
})

Tab:AddButton({
	Name = "Jumppower!",
	Callback = function()
      		game.Players.LocalPlayer.Character.Humanoid.JumpPower = 120
  	end    
})

Tab:AddButton({
	Name = "Reset W/J",
	Callback = function()
      		game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 16
			game.Players.LocalPlayer.Character.Humanoid.JumpPower = 50
  	end    
})

Tab:AddButton({
	Name = "Double Jump",
	Callback = function()
			game.Players.LocalPlayer.Character.Humanoid.JumpPower = 100
  	end    
})

Tab:AddButton({
	Name = "Ultimate Trolling GUI | UTG V3 (MIGHT NOT BE FE. and might be patched)",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/Blukez/Scripts/main/UTG%20V3%20RAW"))()
  	end    
})

Tab:AddButton({
	Name = "Become a Snake Might be patched too",
	Callback = function()
		loadstring(game:HttpGet(('https://pastefy.ga/tWBTcE4R/raw'),true))()
  	end    
})
 
Tab:AddButton({
	Name = "Fly R6 (E TO STOP)",
	Callback = function()
      		loadstring(game:HttpGet("https://pastebin.com/raw/KfNPZgjW"))()
  	end    
})

Tab:AddButton({
	Name = "FE BUILD TOOLS R6 ONLY MIGHT BE PATCHED",
	Callback = function()
      		loadstring(game:HttpGet("https://raw.githubusercontent.com/rouxhaver/scripts/main/FE%20BTools.lua"))()
  	end    
})
 
Tab:AddButton({
	Name = "Ben Script (No Sounds)",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/BlastingStone/MyLuaStuff/master/benscriptgui.lua"))()
  	end    
})

Tab:AddButton({
	Name = "FE brook haven admin",
	Callback = function()
		loadstring(game:HttpGet("https://gist.githubusercontent.com/testttbqwebg/adc0db730f5dfca0d8dbdb81f3b65391/raw/b0443888c4399af5a297cb1100a4749c65705711/qweqw", true))()
  	end    
})


Tab:AddButton({
	Name = "Fly R15 (E TO STOP)",
	Callback = function()
      					repeat wait()
    until game.Players.LocalPlayer and game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:findFirstChild("UpperTorso") and game.Players.LocalPlayer.Character:findFirstChild("Humanoid")
local mouse = game.Players.LocalPlayer:GetMouse()
repeat wait() until mouse
local plr = game.Players.LocalPlayer
local torso = plr.Character.UpperTorso
local flying = true
local deb = true
local ctrl = {f = 0, b = 0, l = 0, r = 0}
local lastctrl = {f = 0, b = 0, l = 0, r = 0}
local maxspeed = 50
local speed = 0
 
function Fly()
local bg = Instance.new("BodyGyro", torso)
bg.P = 9e4
bg.maxTorque = Vector3.new(9e9, 9e9, 9e9)
bg.cframe = torso.CFrame
local bv = Instance.new("BodyVelocity", torso)
bv.velocity = Vector3.new(0,0.1,0)
bv.maxForce = Vector3.new(9e9, 9e9, 9e9)
repeat wait()
plr.Character.Humanoid.PlatformStand = true
if ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0 then
speed = speed+.5+(speed/maxspeed)
if speed > maxspeed then
speed = maxspeed
end
elseif not (ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0) and speed ~= 0 then
speed = speed-1
if speed < 0 then
speed = 0
end
end
if (ctrl.l + ctrl.r) ~= 0 or (ctrl.f + ctrl.b) ~= 0 then
bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (ctrl.f+ctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(ctrl.l+ctrl.r,(ctrl.f+ctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed
lastctrl = {f = ctrl.f, b = ctrl.b, l = ctrl.l, r = ctrl.r}
elseif (ctrl.l + ctrl.r) == 0 and (ctrl.f + ctrl.b) == 0 and speed ~= 0 then
bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (lastctrl.f+lastctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(lastctrl.l+lastctrl.r,(lastctrl.f+lastctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed
else
bv.velocity = Vector3.new(0,0.1,0)
end
bg.cframe = game.Workspace.CurrentCamera.CoordinateFrame * CFrame.Angles(-math.rad((ctrl.f+ctrl.b)*50*speed/maxspeed),0,0)
until not flying
ctrl = {f = 0, b = 0, l = 0, r = 0}
lastctrl = {f = 0, b = 0, l = 0, r = 0}
speed = 0
bg:Destroy()
bv:Destroy()
plr.Character.Humanoid.PlatformStand = false
end
mouse.KeyDown:connect(function(key)
if key:lower() == "e" then
if flying then flying = false
else
flying = true
Fly()
end
elseif key:lower() == "w" then
ctrl.f = 1
elseif key:lower() == "s" then
ctrl.b = -1
elseif key:lower() == "a" then
ctrl.l = -1
elseif key:lower() == "d" then
ctrl.r = 1
end
end)
mouse.KeyUp:connect(function(key)
if key:lower() == "w" then
ctrl.f = 0
elseif key:lower() == "s" then
ctrl.b = 0
elseif key:lower() == "a" then
ctrl.l = 0
elseif key:lower() == "d" then
ctrl.r = 0
end
end)
Fly()
  	end    
})
 
 
