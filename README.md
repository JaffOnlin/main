
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/Vcsk/UI-Library/main/Source/MyUILib(Unamed).lua"))();
local Window = Library:Create("Jaff")

local ToggleGui = Instance.new("ScreenGui")
local Toggle = Instance.new("TextButton")

ToggleGui.Name = "ToggleGui_HE"
ToggleGui.Parent = game.CoreGui

Toggle.Name = "Toggle"
Toggle.Parent = ToggleGui
Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Toggle.BackgroundTransparency = 0.660
Toggle.Position = UDim2.new(0, 0, 0.454706937, 0)
Toggle.Size = UDim2.new(0.0650164187, 0, 0.0888099447, 0)
Toggle.Font = Enum.Font.SourceSans
Toggle.Text = "Toggle"
Toggle.TextScaled = true
Toggle.TextColor3 = Color3.fromRGB(248, 248, 248)
Toggle.TextSize = 24.000
Toggle.TextXAlignment = Enum.TextXAlignment.Left
Toggle.Active = true
Toggle.Draggable = true
Toggle.MouseButton1Click:connect(function()
    Library:ToggleUI()
end)

local MainTab = Window:Tab("Main","rbxassetid://10888331510")
local PlayerTab = Window:Tab("Players","rbxassetid://12296135476")
local VisualTab = Window:Tab("Visuals","rbxassetid://12308581351")
local ExtraTab =
Window:Tab("Extra","rbxassetid://7734042071")

MainTab:Section("God Mod")




MainTab:InfoLabel("Put off to escape (Bot's Only)")

MainTab:Button("On", function()
game.Players.LocalPlayer.Character.Head.CanTouch = false
game.Players.LocalPlayer.Character.LeftFoot.CanTouch = false
game.Players.LocalPlayer.Character.RightFoot.CanTouch = false
game.Players.LocalPlayer.Character.RightHand.CanTouch = false
game.Players.LocalPlayer.Character.LeftHand.CanTouch = false
game.Players.LocalPlayer.Character.RightLowerLeg.CanTouch = false
game.Players.LocalPlayer.Character.RightUpperLeg.CanTouch = false
game.Players.LocalPlayer.Character.LeftLowerLeg.CanTouch = false
game.Players.LocalPlayer.Character.LeftUpperLeg.CanTouch = false
game.Players.LocalPlayer.Character.LeftLowerArm.CanTouch = false
game.Players.LocalPlayer.Character.LeftUpperArm.CanTouch = false
game.Players.LocalPlayer.Character.RightUpperArm.CanTouch = false
game.Players.LocalPlayer.Character.RightLowerArm.CanTouch = false
game.Players.LocalPlayer.Character.UpperTorso.CanTouch = false
game.Players.LocalPlayer.Character.LowerTorso.CanTouch = false
game.Players.LocalPlayer.Character.HumanoidRootPart.CanTouch = false
end)
MainTab:Button("Off", function()
game.Players.LocalPlayer.Character.Head.CanTouch = true
game.Players.LocalPlayer.Character.LeftFoot.CanTouch = true
game.Players.LocalPlayer.Character.RightFoot.CanTouch = true
game.Players.LocalPlayer.Character.RightHand.CanTouch = true
game.Players.LocalPlayer.Character.LeftHand.CanTouch = true
game.Players.LocalPlayer.Character.RightLowerLeg.CanTouch = true
game.Players.LocalPlayer.Character.RightUpperLeg.CanTouch = true
game.Players.LocalPlayer.Character.LeftLowerLeg.CanTouch = true
game.Players.LocalPlayer.Character.LeftUpperLeg.CanTouch = true
game.Players.LocalPlayer.Character.LeftLowerArm.CanTouch = true
game.Players.LocalPlayer.Character.LeftUpperArm.CanTouch = true
game.Players.LocalPlayer.Character.RightUpperArm.CanTouch = true
game.Players.LocalPlayer.Character.RightLowerArm.CanTouch = true
game.Players.LocalPlayer.Character.UpperTorso.CanTouch = true
game.Players.LocalPlayer.Character.LowerTorso.CanTouch = true
game.Players.LocalPlayer.Character.HumanoidRootPart.CanTouch = true
end)

MainTab:Button("Fly", function()
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

local flyingEnabled = false -- Set to true to start flying, false to stop flying
local flySpeed = 50 -- Adjust fly speed as needed

-- Function to start flying
local function startFlying()
    local bodyGyro = Instance.new("BodyGyro")
    local bodyVelocity = Instance.new("BodyVelocity")

    bodyGyro.P = 9e4
    bodyGyro.maxTorque = Vector3.new(9e4, 9e4, 9e4)
    bodyGyro.cframe = humanoidRootPart.CFrame
    bodyGyro.Parent = humanoidRootPart

    bodyVelocity.velocity = Vector3.new(0, 0, 0)
    bodyVelocity.maxForce = Vector3.new(9e4, 9e4, 9e4)
    bodyVelocity.Parent = humanoidRootPart

    while flyingEnabled do
        local moveDirection = Vector3.new()
        local camera = workspace.CurrentCamera
        local cameraCFrame = camera.CFrame

        -- WASD controls for movement
        if player.Character.Humanoid.MoveDirection.Magnitude > 0 then
            moveDirection = cameraCFrame:VectorToWorldSpace(Vector3.new(player.Character.Humanoid.MoveDirection.X, player.Character.Humanoid.MoveDirection.Y, player.Character.Humanoid.MoveDirection.Z))
        end

        bodyVelocity.velocity = moveDirection * flySpeed
        bodyGyro.cframe = cameraCFrame

        wait() -- Wait for the next frame
    end

    -- Clean up after flying is disabled
    bodyGyro:Destroy()
    bodyVelocity:Destroy()
end

-- Function to toggle flying on or off
local function toggleFlying(state)
    flyingEnabled = state
    if flyingEnabled then
        startFlying()
    end
end

if flyingEnabled then 
toggleFlying(false)
elseif flyingEnabled == false then 
toggleFlying(true)
end
end)


MainTab:Button("Item gui (Book 1)", function()

local PiggyGui = Instance.new("ScreenGui")
PiggyGui.Name = "PiggyGui"
PiggyGui.Parent = game.CoreGui

-- Create ScrollingFrame
local ScrollingFrame = Instance.new("ScrollingFrame", PiggyGui)
ScrollingFrame.BackgroundColor3 = Color3.new(0.15, 0.15, 0.15)
ScrollingFrame.Position = UDim2.new(0.18, 0, 0.42, 0)  -- Move to the right
ScrollingFrame.Size = UDim2.new(0, 300, 0, 400)  -- Larger size
ScrollingFrame.Visible = false  -- Initially hidden

-- Create Toggle Button
local ToggleButton = Instance.new("TextButton", PiggyGui)
ToggleButton.Name = "ToggleButton"
ToggleButton.Size = UDim2.new(0, 50, 0, 50)
ToggleButton.Position = UDim2.new(0.85, 0,0.133, 0)  -- Center of the screen
ToggleButton.Text = "IG"
ToggleButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
ToggleButton.TextColor3 = Color3.new(1, 1, 1)
ToggleButton.Active = true
ToggleButton.BorderSizePixel = 0
ToggleButton.BackgroundTransparency = 0.5
ToggleButton.ClipsDescendants = true

-- Make ToggleButton draggable
local draggingToggle
local dragInputToggle
local dragStartToggle
local startPosToggle

local function updateToggle(input)
    local delta = input.Position - dragStartToggle
    ToggleButton.Position = UDim2.new(startPosToggle.X.Scale, startPosToggle.X.Offset + delta.X, startPosToggle.Y.Scale, startPosToggle.Y.Offset + delta.Y)
end

ToggleButton.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
        draggingToggle = true
        dragStartToggle = input.Position
        startPosToggle = ToggleButton.Position

        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                draggingToggle = false
            end
        end)
    end
end)

ToggleButton.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
        dragInputToggle = input
    end
end)

game:GetService("UserInputService").InputChanged:Connect(function(input)
    if input == dragInputToggle and draggingToggle then
        updateToggle(input)
    end
end)

-- Toggle ScrollingFrame visibility
ToggleButton.MouseButton1Click:Connect(function()
    ScrollingFrame.Visible = not ScrollingFrame.Visible
end)

-- Create UIGridLayout
local UIGridLayout = Instance.new("UIGridLayout", ScrollingFrame)
UIGridLayout.CellSize = UDim2.new(0, 90, 0, 90)

-- Update items periodically
while wait(1) do
    if ScrollingFrame.Visible then
        local a = workspace:GetDescendants()
        local items = {}
        local itemframes = ScrollingFrame:GetChildren()

        -- Clear existing item frames
        for _, frame in ipairs(itemframes) do
            if frame.ClassName == "TextButton" then
                frame:Destroy()
            end
        end

        -- Find items to display
        for _, obj in ipairs(a) do
            if obj.Name == "ItemPickupScript" and obj.Parent:FindFirstChild("ClickDetector") then
                table.insert(items, obj.Parent)
            end
        end

        -- Create new item frames
        for _, item in ipairs(items) do
            local ItemFrame = Instance.new("TextButton", ScrollingFrame)
            ItemFrame.Name = "ItemFrame"
            ItemFrame.BackgroundColor3 = Color3.new(1, 1, 1)
            ItemFrame.BackgroundTransparency = 0.95
            ItemFrame.Size = UDim2.new(0, 100, 0, 100)
            ItemFrame.Text = ""

            local View = Instance.new("ViewportFrame", ItemFrame)
            View.Name = "View"
            View.Size = UDim2.new(1, 0, 1, 0)
            View.BackgroundTransparency = 1
            View.BorderSizePixel = 0

            local viewportclone = item:Clone()
            viewportclone.Parent = View

            local cam = Instance.new("Camera", View)
            cam.CameraType = Enum.CameraType.Fixed
            local objectPosition = item.Position
            local cameraPosition = objectPosition + Vector3.new(0, 3, 0)
            cam.CFrame = CFrame.new(cameraPosition, objectPosition)
            View.CurrentCamera = cam

            ItemFrame.MouseButton1Down:Connect(function()
                if item:FindFirstChild("ClickDetector") then
                    local player = game.Players.LocalPlayer
                    local character = player.Character
                    if character and character:FindFirstChild("HumanoidRootPart") then
                        local cpos = character.HumanoidRootPart.CFrame
                        wait(0.05)
                        character.HumanoidRootPart.CFrame = item.CFrame
                        wait(0.1)
                        fireclickdetector(item.ClickDetector)
                        wait(0.3)
                        character.HumanoidRootPart.CFrame = cpos
                    end
                end
            end)
        end
    end
end
end)

MainTab:Button("Item gui & Fly (Book 2)", function()

local PiggyGui = Instance.new("ScreenGui")
PiggyGui.Name = "PiggyGui"
PiggyGui.Parent = game.CoreGui

-- Create ScrollingFrame
local ScrollingFrame = Instance.new("ScrollingFrame", PiggyGui)
ScrollingFrame.BackgroundColor3 = Color3.new(0.15, 0.15, 0.15)
ScrollingFrame.Position = UDim2.new(0.18, 0, 0.42, 0)  -- Move to the right
ScrollingFrame.Size = UDim2.new(0, 300, 0, 400)  -- Larger size
ScrollingFrame.Visible = false  -- Initially hidden

-- Create Toggle Button
local ToggleButton = Instance.new("TextButton", PiggyGui)
ToggleButton.Name = "ToggleButton"
ToggleButton.Size = UDim2.new(0, 50, 0, 50)
ToggleButton.Position = UDim2.new(0.85, 0,0.133, 0)  -- Center of the screen
ToggleButton.Text = "IG"
ToggleButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
ToggleButton.TextColor3 = Color3.new(1, 1, 1)
ToggleButton.Active = true
ToggleButton.BorderSizePixel = 0
ToggleButton.BackgroundTransparency = 0.5
ToggleButton.ClipsDescendants = true

-- Make ToggleButton draggable
local draggingToggle
local dragInputToggle
local dragStartToggle
local startPosToggle

local function updateToggle(input)
    local delta = input.Position - dragStartToggle
    ToggleButton.Position = UDim2.new(startPosToggle.X.Scale, startPosToggle.X.Offset + delta.X, startPosToggle.Y.Scale, startPosToggle.Y.Offset + delta.Y)
end

ToggleButton.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
        draggingToggle = true
        dragStartToggle = input.Position
        startPosToggle = ToggleButton.Position

        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                draggingToggle = false
            end
        end)
    end
end)

ToggleButton.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
        dragInputToggle = input
    end
end)

game:GetService("UserInputService").InputChanged:Connect(function(input)
    if input == dragInputToggle and draggingToggle then
        updateToggle(input)
    end
end)

-- Toggle ScrollingFrame visibility
ToggleButton.MouseButton1Click:Connect(function()
    ScrollingFrame.Visible = not ScrollingFrame.Visible
end)

-- Create UIGridLayout
local UIGridLayout = Instance.new("UIGridLayout", ScrollingFrame)
UIGridLayout.CellSize = UDim2.new(0, 90, 0, 90)

-- Update items periodically
while wait(1) do
    if ScrollingFrame.Visible then
        local a = workspace:GetDescendants()
        local items = {}
        local itemframes = ScrollingFrame:GetChildren()

        -- Clear existing item frames
        for _, frame in ipairs(itemframes) do
            if frame.ClassName == "TextButton" then
                frame:Destroy()
            end
        end

        -- Find items to display
        for _, obj in ipairs(a) do
            if obj.Name == "NewItemPickupScript" and obj.Parent:FindFirstChild("ClickDetector") then
                table.insert(items, obj.Parent)
            end
        end

        -- Create new item frames
        for _, item in ipairs(items) do
            local ItemFrame = Instance.new("TextButton", ScrollingFrame)
            ItemFrame.Name = "ItemFrame"
            ItemFrame.BackgroundColor3 = Color3.new(1, 1, 1)
            ItemFrame.BackgroundTransparency = 0.95
            ItemFrame.Size = UDim2.new(0, 100, 0, 100)
            ItemFrame.Text = ""

            local View = Instance.new("ViewportFrame", ItemFrame)
            View.Name = "View"
            View.Size = UDim2.new(1, 0, 1, 0)
            View.BackgroundTransparency = 1
            View.BorderSizePixel = 0

            local viewportclone = item:Clone()
            viewportclone.Parent = View

            local cam = Instance.new("Camera", View)
            cam.CameraType = Enum.CameraType.Fixed
            local objectPosition = item.Position
            local cameraPosition = objectPosition + Vector3.new(0, 3, 0)
            cam.CFrame = CFrame.new(cameraPosition, objectPosition)
            View.CurrentCamera = cam

            ItemFrame.MouseButton1Down:Connect(function()
                if item:FindFirstChild("ClickDetector") then
                    local player = game.Players.LocalPlayer
                    local character = player.Character
                    if character and character:FindFirstChild("HumanoidRootPart") then
                        local cpos = character.HumanoidRootPart.CFrame
                        wait(0.05)
                        character.HumanoidRootPart.CFrame = item.CFrame
                        wait(0.1)
                        fireclickdetector(item.ClickDetector)
                        wait(0.3)
                        character.HumanoidRootPart.CFrame = cpos
                    end
                end
            end)
        end
    end
end
end)

MainTab:Button("Noclip", function()

local Noclip = nil
local Clip = nil

function noclip()
	Clip = false
	local function Nocl()
		if Clip == false and game.Players.LocalPlayer.Character ~= nil then
			for _,v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
				if v:IsA('BasePart') and v.CanCollide and v.Name ~= floatName then
					v.CanCollide = false
				end
			end
		end
		wait(0.21) -- basic optimization
	end
	Noclip = game:GetService('RunService').Stepped:Connect(Nocl)
end

function clip()
	if Noclip then Noclip:Disconnect() end
	Clip = true
end

noclip()
end)

PlayerTab:TextBox("WalkSpeed", function(value)
    getgenv().WalkSpeed = value
      local Player = game:service'Players'.LocalPlayer;
Player.Character.Humanoid:GetPropertyChangedSignal'WalkSpeed':Connect(function()
Player.Character.Humanoid.WalkSpeed = getgenv().WalkSpeed;
end)

end)

PlayerTab:TextBox("JumpPower", function(value)
    getgenv().Jumppower = value
    pcall(function()
        game:GetService("Players").LocalPlayer.Character.Humanoid.JumpPower = value
    end)
end)

PlayerTab:Slider("Fov", 70,120, function(v)
     game.Workspace.CurrentCamera.FieldOfView = v
end)


PlayerTab:Toggle("Infinite Jump", function(s)
getgenv().InfJ = s
    game:GetService("UserInputService").JumpRequest:connect(function()
        if InfJ == true then
            game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
        end
    end)
end)

PlayerTab:Button("Rejoin", function()
    game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer)
end)

PlayerTab:Button("Serverhop", function()

 local Http = game:GetService("HttpService")

local TPS = game:GetService("TeleportService")

local Api = "https://games.roblox.com/v1/games/"




local _place = game.PlaceId

local _servers = Api.._place.."/servers/Public?sortOrder=Asc&limit=100"

function ListServers(cursor)

   local Raw = game:HttpGet(_servers .. ((cursor and "&cursor="..cursor) or ""))

   return Http:JSONDecode(Raw)

end




local Server, Next; repeat

   local Servers = ListServers(Next)

   Server = Servers.data[1]

   Next = Servers.nextPageCursor

until Server




TPS:TeleportToPlaceInstance(_place,Server.id,game.Players.LocalPlayer)

end)

VisualTab:InfoLabel("Wait 3-10 seconds")

VisualTab:Toggle("Character Highlight", function(state)
getgenv().enabled = state --Toggle on/off
getgenv().filluseteamcolor = true --Toggle fill color using player team color on/off
getgenv().outlineuseteamcolor = true --Toggle outline color using player team color on/off
getgenv().fillcolor = Color3.new(0, 0, 0) --Change fill color, no need to edit if using team color
getgenv().outlinecolor = Color3.new(1, 1, 1) --Change outline color, no need to edit if using team color
getgenv().filltrans = 0.5 --Change fill transparency
getgenv().outlinetrans = 0.5 --Change outline transparency

loadstring(game:HttpGet("https://raw.githubusercontent.com/Vcsk/RobloxScripts/main/Highlight-ESP.lua"))()
end)

VisualTab:Toggle("(Everyone) ESP Name", function(state)
    getgenv().ESPName = state
end)

local c = workspace.CurrentCamera
local ps = game:GetService("Players")
local lp = ps.LocalPlayer
local rs = game:GetService("RunService")

local function esp(p,cr)
	local h = cr:WaitForChild("Humanoid")
	local hrp = cr:WaitForChild("Head")

	local text = Drawing.new("Text")
	text.Visible = false
	text.Center = true
	text.Outline = false 
	text.Font = 3
	text.Size = 16.16
	text.Color = Color3.new(0,255,0)

	local conection
	local conection2
	local conection3

	local function dc()
		text.Visible = false
		text:Remove()
		if conection then
			conection:Disconnect()
			conection = nil 
		end
		if conection2 then
			conection2:Disconnect()
			conection2 = nil 
		end
		if conection3 then
			conection3:Disconnect()
			conection3 = nil 
		end
	end

	conection2 = cr.AncestryChanged:Connect(function(_,parent)
		if not parent then
			dc()
		end
	end)

	conection3 = h.HealthChanged:Connect(function(v)
		if (v<=0) or (h:GetState() == Enum.HumanoidStateType.Dead) then
			dc()
		end
	end)

	conection = rs.RenderStepped:Connect(function()
		local hrp_pos,hrp_onscreen = c:WorldToViewportPoint(hrp.Position)
		if hrp_onscreen and ESPName == true then
			text.Position = Vector2.new(hrp_pos.X, hrp_pos.Y - 27)
			text.Text = p.DisplayName.." (@"..p.Name..")"
			text.Visible = true
		else
			text.Visible = false
		end
	end)
end

local function p_added(p)
	if p.Character then
		esp(p,p.Character)
	end
	p.CharacterAdded:Connect(function(cr)
		esp(p,cr)
	end)
end

for i,p in next, ps:GetPlayers() do 
	if p ~= lp then
		p_added(p)
	end
end

ps.PlayerAdded:Connect(p_added)


ExtraTab:InfoLabel("Others Script's")

ExtraTab:Button("Time (Post-Hunt)",function ()
loadstring(game:HttpGet(('https://raw.githubusercontent.com/BaconBossScript/Piggy/main/Piggy'),true))()
end)

ExtraTab:Button("Secret Badge",function ()
loadstring(game:HttpGet(('https://pastefy.app/iWChQoQo/raw'),true))()
end)

ExtraTab:Button("??? (Badge)",function ()
loadstring(game:HttpGet("https://raw.githubusercontent.com/ToraIsMe2/ToraIsMe2/main/0piggy2", true))()
end)
 
		local NotifyLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/vKhonshu/intro/main/ui"))()
		NotifyLib.prompt('Piggy', 'loaded', 2)
		NotifyLib.prompt('Made by', 'icyscythe', 5)
