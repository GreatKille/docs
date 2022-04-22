if not isfile("KavoConfig.JSON") then writefile("KavoConfig.JSON","{}")
end
game:GetService("StarterGui"):SetCore("SendNotification",{
    Title = "SotryNight V1", -- Title of notification  Text = "story night" has been injected", -- Description of the notification
    Duration = 6 -- How long the notification will be on they're screen
})
wait(3)
local function GetURL(scripturl)
  return game:HttpGet("https://raw.githubusercontent.com/BOYLABOAKO/SyctronicX4ROBLOX/main/"..scripturl, true)
end
local players = game:GetService("Players")
local lplr = players.LocalPlayer
local bedwars = {}
local kavo = loadstring(GetURL("Libraries/kavo.lua"))()
local window = kavo.CreateLib("My firstscript", "RedBerry")

local MainToggle = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local ToggleBtn = Instance.new("ImageButton")

MainToggle.Name = "MainToggle"
MainToggle.Parent = game.CoreGui
MainToggle.ResetOnSpawn = false

Frame.Parent = MainToggle
Frame.BackgroundColor3 = Color3.fromRGB(24, 24, 24)
Frame.BackgroundTransparency = 0.200
Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0.0109622413, 0, 0.0136186769, 0)
Frame.Size = UDim2.new(0, 100, 0, 100)

UICorner.Parent = Frame

ToggleBtn.Name = "ToggleBtn"
ToggleBtn.Parent = Frame
ToggleBtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ToggleBtn.BackgroundTransparency = 1.000
ToggleBtn.Size = UDim2.new(1, 0, 1, 0)
ToggleBtn.Image = "rbxassetid://9423059734"
ToggleBtn.MouseButton1Down:connect(function()
  kavo:ToggleUI()
end)

local function TJTYGU_fake_script()
	local script = Instance.new('LocalScript', ToggleBtn)

	function zigzag(X) return math.acos(math.cos(X*math.pi))/math.pi end
	
	counter = 0
	
	while wait(0.1)do
		script.Parent.ImageColor3 = Color3.fromHSV(zigzag(counter),1,1)
	
		counter = counter + 0.01
	end
end
coroutine.wrap(TJTYGU_fake_script)()


local prophunt= window:NewTab("prophunt")
local Credit = window:NewTab("Credit")


local Vamp = Credit:NewSection("Vamp")
local TheGreatKiller = Credit:NewSection("TheGreatKiller")
local InfJump = prophunt:NewSection("InfJump")
local InfiniteJumpEnabled = true
game:GetService("UserInputService").JumpRequest:connect(function()
	if InfiniteJumpEnabled then	game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
	end
end)
local FovChanger = prophunt:NewSection("FovChanger")
Workspace.CurrentCamera.FieldOfView = 140
local KillAll = prophunt:NewSection("KillAll")
KillAll:NewToggle("KillAll", "local LocalPlayer = game.Players.LocalPlayer
while wait() do
    for i, v in next, game.Players:GetChildren() do
        if v ~= LocalPlayer then
            pcall(
                function()
                    local args = {
                        [1] = LocalPlayer.Character.HumanoidRootPart.CFrame.p,
                        [2] = CFrame.lookAt(
                            LocalPlayer.Character.HumanoidRootPart.CFrame.p,
                            v.Character.HumanoidRootPart.CFrame.p
                        ).lookVector *
                            (v.Character.HumanoidRootPart.CFrame.p - LocalPlayer.Character.HumanoidRootPart.CFrame.p).magnitude,
                        [3] = {
                            ["instance"] = v.Character.HumanoidRootPart,
                            ["normal"] = Vector3.new(1, 0, 0),
                            ["position"] = v.Character.HumanoidRootPart.Position
                        },
                        [4] = math.random(),
                        [5] = false
                    }
                    game:GetService("ReplicatedStorage"):FindFirstChild("events-shared/networking@NetEvents").shoot:FireServer(
                        unpack(args)
                    )
                end
            )
        end
    end
end", function(callback) if callback then print("Toggle On") else print("Toggle Off") end end)


