-- Jailbreaker V1.4 Made By RedBoy /Cloudy
local plr = game:GetService("Players").LocalPlayer
 
 
local TpMethod = 2
 
 
 
 function JailbreakTp(...)
	getfenv()["TpMethod" .. TpMethod](...)
end
 
function TpMethod1(...)
	local char = plr.Character
	local root = char.HumanoidRootPart
	local args = {...}
	for i=0,1,0.05 do
		wait()
		root.CFrame = root.CFrame:lerp(CFrame.new(unpack(args,1,3)), i)
	end
end
 
function TpMethod2(...)
	local args = {...}
	local char = plr.Character
	local target = Vector3.new(unpack(args,1,3))
	local dist = (char:WaitForChild"HumanoidRootPart".Position - target).magnitude
	dist = math.floor(dist / 100) + 1
	for i=0,dist * 4 do
		wait()
		char:MoveTo(Vector3.new(...))
	end
	if args[#args] == true then
		wait()
		char:WaitForChild'HumanoidRootPart'.CFrame = CFrame.new(unpack(args,1,#args - 1))
	end
end
 
function Tween(obj, t, properties)
	local TweenService = game:GetService("TweenService")
	local tweenInfo = TweenInfo.new(t,Enum.EasingStyle.Linear,Enum.EasingDirection.In,0,false,0)
	local tween = TweenService:Create(obj,tweenInfo,properties)
	tween:Play()
	return tween
end
--Properties:
Jailbreakerv14.Name = "Jailbreaker v1.4"
Jailbreakerv14.Parent = game.CoreGui
 
Main.Name = "Main"
Main.Parent = Jailbreakerv14
Main.Active = true
Main.BackgroundColor3 = Color3.new(0.282353, 0.282353, 0.282353)
Main.BackgroundTransparency = 0.10000000149012
Main.Position = UDim2.new(0.879999995, 0, 0.400000006, 0)
Main.Size = UDim2.new(0, 150, 0, 200)
 
TextLabel.Parent = Main
TextLabel.BackgroundColor3 = Color3.new(1, 1, 1)
TextLabel.BackgroundTransparency = 1
TextLabel.Size = UDim2.new(0, 150, 0, 50)
TextLabel.Font = Enum.Font.Cartoon
TextLabel.Text = "Jailbreaker"
TextLabel.TextColor3 = Color3.new(1, 1, 1)
TextLabel.TextScaled = true
TextLabel.TextSize = 14
TextLabel.TextWrapped = true
 
ImageLabel.Parent = Main
ImageLabel.BackgroundColor3 = Color3.new(1, 1, 1)
ImageLabel.BackgroundTransparency = 1
ImageLabel.BorderSizePixel = 0
ImageLabel.Position = UDim2.new(0, 0, 0, 104)
ImageLabel.Size = UDim2.new(0, 150, 0, 75)
ImageLabel.ZIndex = 2
ImageLabel.Image = "http://www.roblox.com/Thumbs/Avatar.ashx?x=100&y=100&userId=1"
 
Name.Name = "Name"
Name.Parent = Main
Name.BackgroundColor3 = Color3.new(1, 1, 1)
Name.BackgroundTransparency = 0.89999997615814
Name.BorderSizePixel = 0
Name.Position = UDim2.new(0, 0, 0, 79)
Name.Size = UDim2.new(0, 150, 0, 20)
Name.Font = Enum.Font.SourceSans
Name.Text = "Player Name"
Name.TextColor3 = Color3.new(1, 1, 1)
Name.TextScaled = true
Name.TextSize = 14
Name.TextWrapped = true
 
Version.Name = "Version"
Version.Parent = Main
Version.BackgroundColor3 = Color3.new(1, 1, 1)
Version.BackgroundTransparency = 0.89999997615814
Version.BorderSizePixel = 0
Version.Position = UDim2.new(-0.666666687, 100, 1.05499995, -32)
Version.Size = UDim2.new(0, 150, 0, 20)
Version.Font = Enum.Font.SourceSans
Version.Text = "Version 1.4"
Version.TextColor3 = Color3.new(1, 1, 1)
Version.TextScaled = true
Version.TextSize = 14
Version.TextWrapped = true
 
Open.Name = "Open"
Open.Parent = Main
Open.BackgroundColor3 = Color3.new(1, 1, 0)
Open.Position = UDim2.new(0, 0, 0.194999993, 0)
Open.Size = UDim2.new(0, 150, 0, 40)
Open.Font = Enum.Font.SourceSans
Open.Text = "Open GUI"
Open.TextColor3 = Color3.new(0, 0, 0)
Open.TextScaled = true
Open.TextSize = 14
Open.TextWrapped = true
Open.MouseButton1Down:connect(function()
    Open.Visible = false
    OTH.Visible = true
    TPS.Visible = true
    AutoRob.Visible = true
    PlayerTP.Visible = true
    Guns.Visible = true
    Close.Visible = true
end)
Close.Name = "Close"
Close.Parent = Main
Close.BackgroundColor3 = Color3.new(1, 1, 0)
Close.Position = UDim2.new(0, 0, 0.194999993, 0)
Close.Size = UDim2.new(0, 150, 0, 40)
Close.Visible = false
Close.Font = Enum.Font.SourceSans
Close.Text = "Close"
Close.TextColor3 = Color3.new(0, 0, 0)
Close.TextScaled = true
Close.TextSize = 14
Close.TextWrapped = true
Close.MouseButton1Down:connect(function()
    Open.Visible = true
    OTH.Visible = false
    TPS.Visible = false
    AutoRob.Visible = false
    PlayerTP.Visible = false
    Guns.Visible = false
    Close.Visible = false
end)
PlayerTP.Name = "PlayerTP"
PlayerTP.Parent = Jailbreakerv14
PlayerTP.Active = true
PlayerTP.BackgroundColor3 = Color3.new(0.247059, 0.247059, 0.247059)
PlayerTP.BackgroundTransparency = 1
PlayerTP.Position = UDim2.new(0.579823673, 0, 0.258893281, 0)
PlayerTP.Size = UDim2.new(0, 150, 0, 312)
PlayerTP.Visible = false
 
PlayerTP_Input.Name = "PlayerTP_Input"
PlayerTP_Input.Parent = PlayerTP
PlayerTP_Input.BackgroundColor3 = Color3.new(1, 0, 0)
PlayerTP_Input.Position = UDim2.new(0, 0, 0.0352564119, 0)
PlayerTP_Input.Size = UDim2.new(0, 150, 0, 50)
PlayerTP_Input.Font = Enum.Font.ArialBold
PlayerTP_Input.Text = "Player Name"
PlayerTP_Input.TextSize = 20
PlayerTP_Input.TextWrapped = true
 
PlayerTP_Teleport.Name = "PlayerTP_Teleport"
PlayerTP_Teleport.Parent = PlayerTP
PlayerTP_Teleport.BackgroundColor3 = Color3.new(0.4, 0.0980392, 1)
PlayerTP_Teleport.Position = UDim2.new(0, 0, 0.25, 0)
PlayerTP_Teleport.Size = UDim2.new(0, 150, 0, 50)
PlayerTP_Teleport.Font = Enum.Font.SourceSansBold
PlayerTP_Teleport.Text = "Teleport To Player"
PlayerTP_Teleport.TextScaled = true
PlayerTP_Teleport.TextSize = 14
PlayerTP_Teleport.TextWrapped = true
 
PTPTEXT.Name = "PTPTEXT"
PTPTEXT.Parent = PlayerTP
PTPTEXT.BackgroundColor3 = Color3.new(0.227451, 0.227451, 0.227451)
PTPTEXT.Position = UDim2.new(0, 0, -0.0799999982, 0)
PTPTEXT.Size = UDim2.new(0, 150, 0, 30)
PTPTEXT.Font = Enum.Font.SourceSans
PTPTEXT.Text = "Player TP"
PTPTEXT.TextColor3 = Color3.new(1, 1, 1)
PTPTEXT.TextScaled = true
PTPTEXT.TextSize = 14
PTPTEXT.TextWrapped = true
 
NameCredits.Name = "Name Credits"
NameCredits.Parent = Jailbreakerv14
NameCredits.BackgroundColor3 = Color3.new(1, 1, 1)
NameCredits.BackgroundTransparency = 1
NameCredits.Position = UDim2.new(0.5, 0, 0.939999998, 0)
NameCredits.Size = UDim2.new(0, 300, 0, 50)
NameCredits.Font = Enum.Font.Cartoon
NameCredits.Text = "Made By RedBoy / Cloudy "
NameCredits.TextColor3 = Color3.new(0, 0, 0)
NameCredits.TextScaled = true
NameCredits.TextSize = 14
NameCredits.TextWrapped = true
 
OTH.Name = "OTH"
OTH.Parent = Jailbreakerv14
OTH.Active = true
OTH.BackgroundColor3 = Color3.new(1, 1, 1)
OTH.BackgroundTransparency = 1
OTH.Position = UDim2.new(0.219999999, 0, 0.104000002, 0)
OTH.Size = UDim2.new(0, 150, 0, 400)
OTH.Visible = false
 
AutoArrest.Name = "AutoArrest"
AutoArrest.Parent = OTH
AutoArrest.BackgroundColor3 = Color3.new(1, 0, 0)
AutoArrest.Size = UDim2.new(0, 150, 0, 30)
AutoArrest.Font = Enum.Font.Cartoon
AutoArrest.Text = "Auto Arrest"
AutoArrest.TextSize = 18
AutoArrest.TextWrapped = true
AutoArrest.MouseButton1Down:connect(function()
local Player = game.Players.LocalPlayer
wait(0.5)
for i,v in pairs(game.Teams.Criminal:GetPlayers()) do
	repeat
	wait()
	Player.Character.HumanoidRootPart.CFrame = v.Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, 1)
	until v.Team.Name ~= "Criminal"
end
 
end)
Btools.Name = "Btools"
Btools.Parent = OTH
Btools.BackgroundColor3 = Color3.new(1, 0, 0)
Btools.Position = UDim2.new(0, 0, 0.5, 0)
Btools.Size = UDim2.new(0, 150, 0, 30)
Btools.Font = Enum.Font.Cartoon
Btools.Text = "Btools"
Btools.TextSize = 18
Btools.TextWrapped = true
Btools.MouseButton1Down:connect(function()
	game.StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Backpack, true)
for index, child in pairs(game:GetService("Workspace"):GetChildren()) do
   if child.ClassName == "Part" then
       child.Locked = false
   end
   if child.ClassName == "MeshPart" then
       child.Locked = false
   end
   if child.ClassName == "UnionOperation" then
       child.Locked = false
   end
   if child.ClassName == "Model" then
       for index, chil in pairs(child:GetChildren()) do
           if chil.ClassName == "Part" then
               chil.Locked = false
           end
           if chil.ClassName == "MeshPart" then
               chil.Locked = false
           end
           if chil.ClassName == "UnionOperation" then
               chil.Locked = false
           end
           if chil.ClassName == "Model" then
               for index, childe in pairs(chil:GetChildren()) do
                   if childe.ClassName == "Part" then
                       childe.Locked = false
                   end
                   if childe.ClassName == "MeshPart" then
                       childe.Locked = false
                   end
                   if childe.ClassName == "UnionOperation" then
                       childe.Locked = false
                   end
                   if childe.ClassName == "Model" then
                       for index, childeo in pairs(childe:GetChildren()) do
                           if childeo.ClassName == "Part" then
                               childeo.Locked = false
                           end
                           if childeo.ClassName == "MeshPart" then
                               childeo.Locked = false
                           end
                           if childeo.ClassName == "UnionOperation" then
                               childeo.Locked = false
                           end
                           if childeo.ClassName == "Model" then
                           end
                       end
                   end
               end
           end
       end
   end
end
c = Instance.new("HopperBin", game:GetService("Players").LocalPlayer.Backpack)
c.BinType = Enum.BinType.Hammer
c = Instance.new("HopperBin", game:GetService("Players").LocalPlayer.Backpack)
c.BinType = Enum.BinType.Clone
c = Instance.new("HopperBin", game:GetService("Players").LocalPlayer.Backpack)
c.BinType = Enum.BinType.Grab
end)
CarFly.Name = "CarFly"
CarFly.Parent = OTH
CarFly.BackgroundColor3 = Color3.new(1, 0, 0)
CarFly.Position = UDim2.new(0, 0, 0.800000012, 0)
CarFly.Size = UDim2.new(0, 150, 0, 30)
CarFly.Font = Enum.Font.Cartoon
CarFly.Text = "Car Fly [R]"
CarFly.TextSize = 18
CarFly.TextWrapped = true
CarFly.MouseButton1Down:connect(function()
	CARFLYR.Visible = true
end)
 
 
 
local plr = game:GetService("Players").LocalPlayer
local m = plr:GetMouse()
m.KeyDown:connect(function(k)
if k:byte() == 114 then
plrh = game:GetService'Players'.LocalPlayer.Character:FindFirstChildOfClass'Humanoid'
plrh:ChangeState('Jumping')
wait()
plrh:ChangeState('Seated')
end
end)
Gravity.Name = "Gravity"
Gravity.Parent = OTH
Gravity.BackgroundColor3 = Color3.new(1, 0, 0)
Gravity.Position = UDim2.new(0, 0, 0.200000003, 0)
Gravity.Size = UDim2.new(0, 150, 0, 30)
Gravity.Font = Enum.Font.Cartoon
Gravity.Text = "Gravity"
Gravity.TextSize = 18
Gravity.TextWrapped = true
Gravity.MouseButton1Down:connect(function()
if Gravity == true then
Gravity = false
game.workspace.Gravity = 196.2
Gravity.Text = "Gravity OFF"
else
Gravity = true
game.workspace.Gravity = 45
Gravity.Text = "Gravity ON"
end
end)
InfiniteHealth.Name = "InfiniteHealth"
InfiniteHealth.Parent = OTH
InfiniteHealth.BackgroundColor3 = Color3.new(1, 0, 0)
InfiniteHealth.Position = UDim2.new(0, 0, 0.699999988, 0)
InfiniteHealth.Size = UDim2.new(0, 150, 0, 30)
InfiniteHealth.Font = Enum.Font.Cartoon
InfiniteHealth.Text = "INF Health"
InfiniteHealth.TextSize = 18
InfiniteHealth.TextWrapped = true
InfiniteHealth.MouseButton1Down:connect(function()
	game:GetService("Players").LocalPlayer.Character.Humanoid.Name = 1
local l = game:GetService("Players").LocalPlayer.Character["1"]:Clone()
l.Parent = game:GetService("Players").LocalPlayer.Character
l.Name = "Humanoid"
wait(0.1)
game:GetService("Players").LocalPlayer.Character["1"]:Destroy()
game:GetService("Workspace").CurrentCamera.CameraSubject = game:GetService("Players").LocalPlayer.Character
game:GetService("Players").LocalPlayer.Character.Animate.Disabled = true
wait(0.1)
game:GetService("Players").LocalPlayer.Character.Animate.Disabled = false
game:GetService("Players").LocalPlayer.Character.Humanoid.DisplayDistanceType = "None"
end)
InfiniteNitro.Name = "InfiniteNitro"
InfiniteNitro.Parent = OTH
InfiniteNitro.BackgroundColor3 = Color3.new(1, 0, 0)
InfiniteNitro.Position = UDim2.new(0, 0, 0.600000024, 0)
InfiniteNitro.Size = UDim2.new(0, 150, 0, 30)
InfiniteNitro.Font = Enum.Font.Cartoon
InfiniteNitro.Text = "INF Nitro"
InfiniteNitro.TextSize = 18
InfiniteNitro.TextWrapped = true
InfiniteNitro.MouseButton1Down:connect(function()
	game:GetService('Players').LocalPlayer.PlayerGui.MainGui.Nitro.Name = "69696969"
    game:GetService('Players').LocalPlayer.PlayerGui.ProductGui.Nitro:ClearAllChildren()
end)
Infiniteammo.Name = "Infiniteammo"
Infiniteammo.Parent = OTH
Infiniteammo.BackgroundColor3 = Color3.new(1, 0, 0)
Infiniteammo.Position = UDim2.new(0, 0, 0.899999976, 0)
Infiniteammo.Size = UDim2.new(0, 150, 0, 30)
Infiniteammo.Font = Enum.Font.Cartoon
Infiniteammo.Text = "InfiniteJump"
Infiniteammo.TextSize = 18
Infiniteammo.TextWrapped = true
 
local InfiniteJumpEnabled = true
game:GetService("UserInputService").JumpRequest:connect(function()
	if InfiniteJumpEnabled == true then
		game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
		if InfiniteJumpEnabled == false then
 
		end
	end
	end)
 
Noclip.Name = "Noclip"
Noclip.Parent = OTH
Noclip.BackgroundColor3 = Color3.new(1, 0, 0)
Noclip.Position = UDim2.new(0, 0, 0.400000006, 0)
Noclip.Size = UDim2.new(0, 150, 0, 30)
Noclip.Font = Enum.Font.Cartoon
Noclip.Text = "Noclip [B]"
Noclip.TextSize = 18
Noclip.TextWrapped = true
Noclip.MouseButton1Down:connect(function()
 
	local noclipplayer = game:GetService("Players").LocalPlayer
	local noclipmouse = noclipplayer:GetMouse()
 
	local donoclip = false
	local noclip = false
 
	function b_noclip(key)
		if (key == "b") then
			if noclip == false then
				donoclip = true
 
				noclip = true
			elseif noclip == true then
				donoclip = false
 
				noclip = false
			end
		end
	end
 
	noclipmouse.KeyDown:connect(b_noclip)
 
	game:GetService("Players").LocalPlayer.Character.Head.Touched:connect(function(obj)
		if obj ~= workspace.Terrain then
			if donoclip == true then
				obj.CanCollide = false
			else
				obj.CanCollide = true
			end
		end
	end)
end)
RemoveALL.Name = "RemoveALL"
RemoveALL.Parent = OTH
RemoveALL.BackgroundColor3 = Color3.new(1, 0, 0)
RemoveALL.Position = UDim2.new(0, 0, 0.300000012, 0)
RemoveALL.Size = UDim2.new(0, 150, 0, 30)
RemoveALL.Font = Enum.Font.Cartoon
RemoveALL.Text = "RemoveALL"
RemoveALL.TextSize = 18
RemoveALL.TextWrapped = true
RemoveALL.MouseButton1Down:connect(function()	
	game.Workspace.Cells:Remove()
 
	game.Workspace.Museum.CaseLasers:Remove()
 
	game.Workspace.Museum.Lights:Remove()
 
	game.Workspace.Museum.Doors:Remove()
 
	game.Workspace.EscapeRoutes:Remove()
 
	for i,v in pairs(workspace.Doors:GetChildren()) do
    v:Destroy()
 
	end
end)
 
RemoveALL.MouseButton1Down:connect(function()
	local banklasers = game:GetService("Workspace").Banks:GetChildren()
	banklasers[1].Lasers:Destroy()
end)
 
RemoveALL.MouseButton1Down:connect(function()
local jewelry = game:GetService("Workspace").Jewelrys:GetChildren()
 
	for i = 1,4 do
	local xd = jewelry[1].Model.BarbedWire
	xd:Destroy()
	end
end)
 
RemoveALL.MouseButton1Down:connect(function()
	local banklasers = game:GetService("Workspace").Banks:GetChildren()
	banklasers[1].Door.Model:Destroy()
end)
Walkspeed.Name = "Walkspeed"
Walkspeed.Parent = OTH
Walkspeed.BackgroundColor3 = Color3.new(1, 0, 0)
Walkspeed.Position = UDim2.new(0, 0, 0.100000001, 0)
Walkspeed.Size = UDim2.new(0, 150, 0, 30)
Walkspeed.Font = Enum.Font.Cartoon
Walkspeed.Text = "Walkspeed[X]"
Walkspeed.TextSize = 18
Walkspeed.TextWrapped = true
Walkspeed.MouseButton1Down:connect(function()
	local walkspeedplayer = game:GetService("Players").LocalPlayer
	local walkspeedmouse = walkspeedplayer:GetMouse()
 
	local walkspeedenabled = false
 
	function x_walkspeed(key)
		if (key == "x") then
			if walkspeedenabled == false then
				_G.WS = 200;
				local Humanoid = game:GetService("Players").LocalPlayer.Character.Humanoid;
				Humanoid:GetPropertyChangedSignal("WalkSpeed"):Connect(function()
				Humanoid.WalkSpeed = _G.WS;
				end)
				Humanoid.WalkSpeed = _G.WS;
 
				walkspeedenabled = true
			elseif walkspeedenabled == true then
				_G.WS = 20;
				local Humanoid = game:GetService("Players").LocalPlayer.Character.Humanoid;
				Humanoid:GetPropertyChangedSignal("WalkSpeed"):Connect(function()
				Humanoid.WalkSpeed = _G.WS;
				end)
				Humanoid.WalkSpeed = _G.WS;
 
				walkspeedenabled = false
			end
		end
	end
 
	walkspeedmouse.KeyDown:connect(x_walkspeed)
 
	WALKX.Visible =true
end)
OTHTEXT.Name = "OTHTEXT"
OTHTEXT.Parent = OTH
OTHTEXT.BackgroundColor3 = Color3.new(0.227451, 0.227451, 0.227451)
OTHTEXT.Position = UDim2.new(0, 0, -0.0799999982, 0)
OTHTEXT.Size = UDim2.new(0, 150, 0, 30)
OTHTEXT.Font = Enum.Font.SourceSans
OTHTEXT.Text = "Functions"
OTHTEXT.TextColor3 = Color3.new(1, 1, 1)
OTHTEXT.TextScaled = true
OTHTEXT.TextSize = 14
OTHTEXT.TextWrapped = true
 
TPS.Name = "TPS"
TPS.Parent = Jailbreakerv14
TPS.Active = true
TPS.BackgroundColor3 = Color3.new(1, 1, 1)
TPS.BackgroundTransparency = 1
TPS.Position = UDim2.new(0.0500000007, 0, 0.100000001, 0)
TPS.Size = UDim2.new(0, 150, 0, 400)
TPS.Visible = false
 
BankFront.Name = "BankFront"
BankFront.Parent = TPS
BankFront.BackgroundColor3 = Color3.new(1, 0, 0)
BankFront.Size = UDim2.new(0, 150, 0, 30)
BankFront.Font = Enum.Font.Cartoon
BankFront.Text = "BankFront"
BankFront.TextSize = 18
BankFront.TextWrapped = true
BankFront.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(9.92591476, 17.8639755, 786.788147)
end
end)
BankVault.Name = "BankVault"
BankVault.Parent = TPS
BankVault.BackgroundColor3 = Color3.new(1, 0, 0)
BankVault.Position = UDim2.new(0, 0, 0.100000001, 0)
BankVault.Size = UDim2.new(0, 150, 0, 30)
BankVault.Font = Enum.Font.Cartoon
BankVault.Text = "BankVault"
BankVault.TextSize = 18
BankVault.TextWrapped = true
BankVault.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(18.3854294, 0.765628457, 815.506348)
end
end)
JewIn.Name = "JewIn"
JewIn.Parent = TPS
JewIn.BackgroundColor3 = Color3.new(1, 0, 0)
JewIn.Position = UDim2.new(0, 0, 0.200000003, 0)
JewIn.Size = UDim2.new(0, 150, 0, 30)
JewIn.Font = Enum.Font.Cartoon
JewIn.Text = "Jewelry Inside"
JewIn.TextSize = 18
JewIn.TextWrapped = true
JewIn.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(133.300705, 17.9375954, 1316.42407)
end
end)
JewOut.Name = "JewOut"
JewOut.Parent = TPS
JewOut.BackgroundColor3 = Color3.new(1, 0, 0)
JewOut.Position = UDim2.new(0, 0, 0.300000012, 0)
JewOut.Size = UDim2.new(0, 150, 0, 30)
JewOut.Font = Enum.Font.Cartoon
JewOut.Text = "Jewelry Top"
JewOut.TextSize = 18
JewOut.TextWrapped = true
JewOut.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(101.211128, 98.6576996, 1310.54175)
end
end)
Museum.Name = "Museum"
Museum.Parent = TPS
Museum.BackgroundColor3 = Color3.new(1, 0, 0)
Museum.Position = UDim2.new(0, 0, 0.400000006, 0)
Museum.Size = UDim2.new(0, 150, 0, 30)
Museum.Font = Enum.Font.Cartoon
Museum.Text = "Museum In"
Museum.TextSize = 18
Museum.TextWrapped = true
Museum.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1063.02, 117.562, 1218.757) + Vector3.new(1,0,0)
end
end)
MuseumTop.Name = "MuseumTop"
MuseumTop.Parent = TPS
MuseumTop.BackgroundColor3 = Color3.new(1, 0, 0)
MuseumTop.Position = UDim2.new(0, 0, 0.5, 0)
MuseumTop.Size = UDim2.new(0, 150, 0, 30)
MuseumTop.Font = Enum.Font.Cartoon
MuseumTop.Text = "Museum Roof"
MuseumTop.TextSize = 18
MuseumTop.TextWrapped = true
MuseumTop.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1078.45, 153.904, 1176.52) + Vector3.new(1,0,0)
end
end)
crim1.Name = "crim1"
crim1.Parent = TPS
crim1.BackgroundColor3 = Color3.new(1, 0, 0)
crim1.Position = UDim2.new(0, 0, 0.899999976, 0)
crim1.Size = UDim2.new(0, 150, 0, 30)
crim1.Font = Enum.Font.Cartoon
crim1.Text = "Criminal Base 1"
crim1.TextSize = 18
crim1.TextWrapped = true
crim1.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-221.723099, 17.8924026, 1578.80261)
end
end)
crim2.Name = "crim2"
crim2.Parent = TPS
crim2.BackgroundColor3 = Color3.new(1, 0, 0)
crim2.Position = UDim2.new(0, 0, 0.800000012, 0)
crim2.Size = UDim2.new(0, 150, 0, 30)
crim2.Font = Enum.Font.Cartoon
crim2.Text = "Criminal Base 2"
crim2.TextSize = 18
crim2.TextWrapped = true
crim2.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1650.80896, 49.863636, -1770.66626)
end
end)
donut.Name = "donut"
donut.Parent = TPS
donut.BackgroundColor3 = Color3.new(1, 0, 0)
donut.Position = UDim2.new(0, 0, 0.600000024, 0)
donut.Size = UDim2.new(0, 150, 0, 30)
donut.Font = Enum.Font.Cartoon
donut.Text = "Donut Shop"
donut.TextSize = 18
donut.TextWrapped = true
donut.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(257.191101, 17.81828869, -1753.11206)
end
end)
gas.Name = "gas"
gas.Parent = TPS
gas.BackgroundColor3 = Color3.new(1, 0, 0)
gas.Position = UDim2.new(0, 0, 0.699999988, 0)
gas.Size = UDim2.new(0, 150, 0, 30)
gas.Font = Enum.Font.Cartoon
gas.Text = "Gas Station"
gas.TextSize = 18
gas.TextWrapped = true
gas.MouseButton1Down:connect(function()
for i = 1,45 do
wait(.08)
game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1586.41101, 17.8481865, 709.37262)
end
end)
train.Name = "train"
train.Parent = TPS
train.BackgroundColor3 = Color3.new(1, 0, 0)
train.Position = UDim2.new(0, 0, 1, 0)
train.Size = UDim2.new(0, 150, 0, 30)
train.Font = Enum.Font.Cartoon
train.Text = "Train Spawn"
train.TextSize = 18
train.TextWrapped = true
train.MouseButton1Down:connect(function()
	for i = 1,45 do
wait(.08)
game:GetService('Players').LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1954.95007, 68.0448606, -603.844116)
end
end)
TPTEXT.Name = "TPTEXT"
TPTEXT.Parent = TPS
TPTEXT.BackgroundColor3 = Color3.new(0.227451, 0.227451, 0.227451)
TPTEXT.Position = UDim2.new(0, 0, -0.0799999982, 0)
TPTEXT.Size = UDim2.new(0, 150, 0, 30)
TPTEXT.Font = Enum.Font.SourceSans
TPTEXT.Text = "Teleports"
TPTEXT.TextColor3 = Color3.new(1, 1, 1)
TPTEXT.TextScaled = true
TPTEXT.TextSize = 14
TPTEXT.TextWrapped = true
 
Guns.Name = "Guns"
Guns.Parent = Jailbreakerv14
Guns.Active = true
Guns.BackgroundColor3 = Color3.new(1, 1, 1)
Guns.BackgroundTransparency = 1
Guns.Position = UDim2.new(0.400000006, 0, 0.104000002, 0)
Guns.Size = UDim2.new(0, 150, 0, 400)
Guns.Visible = false
 
AK47.Name = "AK47"
AK47.Parent = Guns
AK47.BackgroundColor3 = Color3.new(1, 0, 0)
AK47.Position = UDim2.new(0, 0, 0.100000001, 0)
AK47.Size = UDim2.new(0, 150, 0, 30)
AK47.Font = Enum.Font.Cartoon
AK47.Text = "AK47"
AK47.TextSize = 18
AK47.TextWrapped = true
AK47.MouseButton1Down:connect(function()
	local hit = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0,0,-3)
 
    a = Instance.new("Part", workspace)
    a.Anchored = true
    a.Position = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0,0,-3)
    a.CanCollide = false
 
        for i, v in pairs(game:GetService("Workspace").Givers:GetChildren()) do
    if v.Name == "ShootingRange" then
    for a, b in pairs(v:GetChildren()) do
    if b:IsA("StringValue") then
    if b.Value == "AK47" then
    v.CFrame = CFrame.new(hit)
    end
    end
    end
    end
    end
end)
M4A4.Name = "M4A4"
M4A4.Parent = Guns
M4A4.BackgroundColor3 = Color3.new(1, 0, 0)
M4A4.Size = UDim2.new(0, 150, 0, 30)
M4A4.Font = Enum.Font.Cartoon
M4A4.Text = "M4A4"
M4A4.TextSize = 18
M4A4.TextWrapped = true
M4A4.MouseButton1Down:connect(function()
	local hit = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0,0,-3)
 
    a = Instance.new("Part", workspace)
    a.Anchored = true
    a.Position = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0,0,-3)
    a.CanCollide = false
 
        for i, v in pairs(game:GetService("Workspace").Givers:GetChildren()) do
    if v.Name == "Station" then
    for a, b in pairs(v:GetChildren()) do
    if b:IsA("StringValue") then
    if b.Value == "RifleSWAT" then
    v.CFrame = CFrame.new(hit)
    end
    end
    end
    end
    end
end)
Pistol.Name = "Pistol"
Pistol.Parent = Guns
Pistol.BackgroundColor3 = Color3.new(1, 0, 0)
Pistol.Position = UDim2.new(0, 0, 0.300000012, 0)
Pistol.Size = UDim2.new(0, 150, 0, 30)
Pistol.Font = Enum.Font.Cartoon
Pistol.Text = "Pistol"
Pistol.TextSize = 18
Pistol.TextWrapped = true
Pistol.MouseButton1Down:connect(function()
	local hit = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0,0,-3)
 
    a = Instance.new("Part", workspace)
    a.Anchored = true
    a.Position = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0,0,-3)
    a.CanCollide = false
 
        for i, v in pairs(game:GetService("Workspace").Givers:GetChildren()) do
    if v.Name == "Station" then
    for a, b in pairs(v:GetChildren()) do
    if b:IsA("StringValue") then
    if b.Value == "Pistol" then
    v.CFrame = CFrame.new(hit)
    end
    end
    end
    end
    end
end)
Shotgun.Name = "Shotgun"
Shotgun.Parent = Guns
Shotgun.BackgroundColor3 = Color3.new(1, 0, 0)
Shotgun.Position = UDim2.new(0, 0, 0.200000003, 0)
Shotgun.Size = UDim2.new(0, 150, 0, 30)
Shotgun.Font = Enum.Font.Cartoon
Shotgun.Text = "Shotgun"
Shotgun.TextSize = 18
Shotgun.TextWrapped = true
Shotgun.MouseButton1Down:connect(function()
	local hit = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0,0,-3)
 
    a = Instance.new("Part", workspace)
    a.Anchored = true
    a.Position = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0,0,-3)
    a.CanCollide = false
 
        for i, v in pairs(game:GetService("Workspace").Givers:GetChildren()) do
    if v.Name == "Station" then
    for a, b in pairs(v:GetChildren()) do
    if b:IsA("StringValue") then
    if b.Value == "Shotgun" then
    v.CFrame = CFrame.new(hit)
    end
    end
    end
    end
    end
end)
GUNSTEXT.Name = "GUNSTEXT"
GUNSTEXT.Parent = Guns
GUNSTEXT.BackgroundColor3 = Color3.new(0.227451, 0.227451, 0.227451)
GUNSTEXT.Position = UDim2.new(0, 0, -0.0799999982, 0)
GUNSTEXT.Size = UDim2.new(0, 150, 0, 30)
GUNSTEXT.Font = Enum.Font.SourceSans
GUNSTEXT.Text = "Guns"
GUNSTEXT.TextColor3 = Color3.new(1, 1, 1)
GUNSTEXT.TextScaled = true
GUNSTEXT.TextSize = 14
GUNSTEXT.TextWrapped = true
 
AutoRob.Name = "Auto Rob"
AutoRob.Parent = Jailbreakerv14
AutoRob.Active = true
AutoRob.BackgroundColor3 = Color3.new(1, 0, 0)
AutoRob.BackgroundTransparency = 1
AutoRob.BorderSizePixel = 0
AutoRob.Position = UDim2.new(0.579999983, 0, 0.104000002, 0)
AutoRob.Size = UDim2.new(0, 150, 0, 400)
AutoRob.Visible = false
 
BankAutoRobBtn.Name = "BankAutoRobBtn"
BankAutoRobBtn.Parent = AutoRob
BankAutoRobBtn.BackgroundColor3 = Color3.new(1, 0, 0)
BankAutoRobBtn.Size = UDim2.new(0, 150, 0, 30)
BankAutoRobBtn.Font = Enum.Font.ArialBold
BankAutoRobBtn.Text = "Bank Auto Rob"
BankAutoRobBtn.TextScaled = true
BankAutoRobBtn.TextSize = 14
BankAutoRobBtn.TextWrapped = true
BankAutoRobBtn.MouseButton1Click:connect(function()
	local Bank = workspace:FindFirstChild("Banks"):GetChildren()[1]
	local Info = Bank.Extra.Sign
	if Info.Decal.Transparency == 0 then
		game:GetService("StarterGui"):SetCore("SendNotification",{
			Title = "Bank is closed!",
			Text = "You need to wait for the bank to open!",
			Duration = 7,
			Button1 = "Dismiss",
		})
		return
	end
	local bankpos = Vector3.new(Info.Position.X,0,Info.Position.Z)
	local root = plr.Character.HumanoidRootPart
	local plrpos = Vector3.new(root.Position.X,0,root.Position.Z)
 
	if (bankpos - plrpos).magnitude > 150 then
		local cb = Instance.new"BindableFunction"
 
		cb.OnInvoke = function(arg)
			if arg == "Teleport" then
				JailbreakTp(10, 18, 784)
			end
		end
 
		game:GetService("StarterGui"):SetCore("SendNotification",{
			Title = "You are too far!",
			Text = "You need to get closer to the bank (use tp)",
			Duration = 7,
			Button1 = "Dismiss",
			Button2 = "Teleport",
			Callback = cb
		})
	else
		RobTheBank()
	end
end)
 
AuTEXT.Name = "AuTEXT"
AuTEXT.Parent = AutoRob
AuTEXT.BackgroundColor3 = Color3.new(0.227451, 0.227451, 0.227451)
AuTEXT.Position = UDim2.new(0, 0, -0.0799999982, 0)
AuTEXT.Size = UDim2.new(0, 150, 0, 30)
AuTEXT.Font = Enum.Font.Cartoon
AuTEXT.Text = "AutoRob"
AuTEXT.TextColor3 = Color3.new(1, 1, 1)
AuTEXT.TextScaled = true
AuTEXT.TextSize = 14
AuTEXT.TextWrapped = true
 
JewelryStatus.Name = "JewelryStatus"
JewelryStatus.Parent = Jailbreakerv14
JewelryStatus.BackgroundColor3 = Color3.new(0, 0.384314, 1)
JewelryStatus.Position = UDim2.new(0.879999995, 0, 0.296000004, 0)
JewelryStatus.Size = UDim2.new(0, 150, 0, 26)
JewelryStatus.Font = Enum.Font.SourceSans
JewelryStatus.Text = "Jewelry:"
JewelryStatus.TextColor3 = Color3.new(0, 0, 0)
JewelryStatus.TextSize = 14
 
BankStatus.Name = "BankStatus"
BankStatus.Parent = Jailbreakerv14
BankStatus.BackgroundColor3 = Color3.new(0, 0.384314, 1)
BankStatus.Position = UDim2.new(0.879999995, 0, 0.349000007, 0)
BankStatus.Size = UDim2.new(0, 150, 0, 26)
BankStatus.Font = Enum.Font.SourceSans
BankStatus.Text = "Bank:"
BankStatus.TextColor3 = Color3.new(0, 0, 0)
BankStatus.TextSize = 14
-- Scripts:
 
PlayerTP_Teleport.MouseButton1Down:connect(function()
	local tp_namedplayer = PlayerTP_Input.Text
	local tp_player = game:GetService("Players")[tp_namedplayer]
	local PLR = game:GetService("Players").LocalPlayer
	local p = PlayerTP_Input.Text
 
	if tp_player then 
			for i = 1,20 do
		wait()
		PLR.Character.HumanoidRootPart.CFrame = tp_player.Character.HumanoidRootPart.CFrame + Vector3.new(0, 3, 0)
		end
	end
end)
 
 
 
 
--AutoRob stuff--
local DuffelBag = game:GetService("MarketplaceService"):PlayerOwnsAsset(plr, 2219040)
local BankAutoRob = {
	{
		Pos = {51, 18.06, 856.5},
		Yield = 2,
		Status = "Starting the robbery"
	},
	{
		Pos = {29.71, 0.73, 815.25},
		Yield = 15,
		Status = "Opening the vault"
	},
	{
		Pos = {18.37, 0.7659, 822.25},
		Yield = DuffelBag and 50 or 49,
		Status = "Collecting $$$"
	},
	{
		Pos = {10, 18, 784},
		Status = "Finishing the robbery"
	}
}
 
local function Tp(...)
	local char = plr.Character
	for i=1,2 do
		wait()
		char:WaitForChild'HumanoidRootPart'.CFrame = CFrame.new(...)
	end
end
 
function RobTheBank()
	for _,v in pairs(BankAutoRob) do
		Tp(unpack(v.Pos))
		wait(v.Yield)
	end
end
 
--Bank notification--
pcall(function()
	local Bank = workspace:FindFirstChild("Banks"):GetChildren()[1]
	local Info = Bank.Extra.Sign.Decal
	Info:GetPropertyChangedSignal("Transparency"):Connect(function()
		if Info.Transparency ~= 0 then
			BankStatus.Text = "Bank:Open"
			BankStatus.TextColor3 = Color3.new(0,1,0)
			BankAutoRobBtn.BackgroundColor3 = Color3.new(0,1,0)
			local cb = Instance.new("BindableFunction")
			cb.OnInvoke = function(arg)
				if arg == "Teleport" then
					JailbreakTp(10, 18, 784)
				elseif arg == "AutoRob" then
					RobTheBank()
				end
			end
			game:GetService("StarterGui"):SetCore("SendNotification",{
				Title = "Bank is ready!",
				Text = "Bank is ready!",
				Duration = 15,
				Button1 = "Dismiss",
				Button2 = (Vector3.new(Info.Parent.Position.X,0,Info.Parent.Position.Z) - Vector3.new(plr.Character.HumanoidRootPart.Position.X,0,plr.Character.HumanoidRootPart.Position.Z)).magnitude < 150 and "AutoRob" or "Teleport",
				Callback = cb
			})
		else
			BankStatus.Text = "Bank:Closed"
			BankStatus.TextColor3 = Color3.new(1,0,0)
			BankAutoRobBtn.BackgroundColor3 = Color3.new(1,0,0)
		end
	end)
	BankStatus.Text = Info.Transparency == 0 and "Bank:Closed" or "Bank:Open"
	BankStatus.TextColor3 = Info.Transparency == 0 and Color3.new(1,0,0) or Color3.new(0,1,0)
	BankAutoRobBtn.BackgroundColor3 = Info.Transparency == 0 and Color3.new(1,0,0) or Color3.new(0,1,0)
end)
--Jewelry notification--
pcall(function()
	local Jewelry = workspace:FindFirstChild("Jewelrys"):GetChildren()[1]
	local Info = Jewelry.Extra.Sign.Decal
	Info:GetPropertyChangedSignal("Transparency"):Connect(function()
		if Info.Transparency ~= 0 then
			JewelryStatus.Text = "Jewelry:Open"
			JewelryStatus.TextColor3 = Color3.new(0,1,0)
			BankStatus.TextColor3 = Color3.new(0,1,0)
			local cb = Instance.new("BindableFunction")
			cb.OnInvoke = function(arg)
				if arg == "Teleport" then
					JailbreakTp(142, 18, 1365)
				end
			end
			game:GetService("StarterGui"):SetCore("SendNotification",{
				Title = "Jewelry is ready!",
				Text = "Jewelry is ready!",
				Duration = 15,
				Button1 = "Dismiss",
				Button2 = "Teleport",
				Callback = cb
			})
		else
			JewelryStatus.Text = "Jewelry:Closed"
			JewelryStatus.TextColor3 = Color3.new(1,0,0)
		end
	end)
	JewelryStatus.Text = Info.Transparency == 0 and "Jewelry:Closed" or "Jewelry:Open"
	JewelryStatus.TextColor3 = Info.Transparency == 0 and Color3.new(1,0,0) or Color3.new(0,1,0)
end)
 
 
 
 
 
 
function SCRIPT_UOJS84_FAKESCRIPT() -- ImageLabel.LocalScript 
	getfenv().script = Instance.new('LocalScript', ImageLabel)
 
	script.Parent.Image = "http://www.roblox.com/Thumbs/Avatar.ashx?x=100&y=100&userId=" .. game.Players.LocalPlayer.UserId
 
end
coroutine.resume(coroutine.create(SCRIPT_UOJS84_FAKESCRIPT))
function SCRIPT_SEDR75_FAKESCRIPT() -- Name.LocalScript 
	getfenv().script = Instance.new('LocalScript', Name)
 
	script.Parent.Text = game.Players.LocalPlayer.Name
 
end
coroutine.resume(coroutine.create(SCRIPT_SEDR75_FAKESCRIPT))
