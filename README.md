-- Project DarkLuaSS v1.0 - Key: DARKSERVERSİDE

local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")
local UserInputService = game:GetService("UserInputService")

local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

local screenGui = Instance.new("ScreenGui")
screenGui.Name = "DarkLuaSS"
screenGui.ResetOnSpawn = false
screenGui.Parent = playerGui

local CORRECT_KEY = "DARKSERVERSİDE"

-- Key Giriş Ekranı
local keyFrame = Instance.new("Frame")
keyFrame.Size = UDim2.new(0, 360, 0, 320)
keyFrame.Position = UDim2.new(0.5, -180, 0.5, -160)
keyFrame.BackgroundColor3 = Color3.fromRGB(18, 18, 18)
keyFrame.BorderSizePixel = 0
keyFrame.Parent = screenGui

Instance.new("UIStroke", keyFrame).Color = Color3.fromRGB(40, 40, 40)
Instance.new("UIStroke", keyFrame).Thickness = 2

local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 70)
title.BackgroundTransparency = 1
title.Text = "Project DarkLuaSS v1.0"
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.TextSize = 21
title.Font = Enum.Font.GothamSemibold
title.Parent = keyFrame

local keyLabel = Instance.new("TextLabel")
keyLabel.Size = UDim2.new(1, -40, 0, 25)
keyLabel.Position = UDim2.new(0, 20, 0, 90)
keyLabel.BackgroundTransparency = 1
keyLabel.Text = "Enter Key"
keyLabel.TextColor3 = Color3.fromRGB(170, 170, 170)
keyLabel.TextSize = 15
keyLabel.Font = Enum.Font.Gotham
keyLabel.TextXAlignment = Enum.TextXAlignment.Left
keyLabel.Parent = keyFrame

local keyBox = Instance.new("TextBox")
keyBox.Size = UDim2.new(1, -40, 0, 45)
keyBox.Position = UDim2.new(0, 20, 0, 120)
keyBox.BackgroundColor3 = Color3.fromRGB(28, 28, 28)
keyBox.TextColor3 = Color3.fromRGB(255, 255, 255)
keyBox.PlaceholderText = "Paste your key here..."
keyBox.Text = ""
keyBox.TextSize = 16
keyBox.Font = Enum.Font.Gotham
keyBox.Parent = keyFrame
Instance.new("UICorner", keyBox).CornerRadius = UDim.new(0, 0)

local submitBtn = Instance.new("TextButton")
submitBtn.Size = UDim2.new(1, -40, 0, 50)
submitBtn.Position = UDim2.new(0, 20, 0, 190)
submitBtn.BackgroundColor3 = Color3.fromRGB(28, 28, 28)
submitBtn.Text = "Submit Key"
submitBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
submitBtn.TextSize = 17
submitBtn.Font = Enum.Font.GothamSemibold
submitBtn.Parent = keyFrame
Instance.new("UIStroke", submitBtn).Color = Color3.fromRGB(55, 55, 55)
Instance.new("UIStroke", submitBtn).Thickness = 1.5

-- Ana Executor GUI
local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 620, 0, 420)
mainFrame.Position = UDim2.new(0.5, -310, 0.5, -210)
mainFrame.BackgroundColor3 = Color3.fromRGB(18, 18, 18)
mainFrame.BorderSizePixel = 0
mainFrame.Visible = false
mainFrame.Parent = screenGui

Instance.new("UIStroke", mainFrame).Color = Color3.fromRGB(40, 40, 40)
Instance.new("UIStroke", mainFrame).Thickness = 2

local titleBar = Instance.new("Frame")
titleBar.Size = UDim2.new(1, 0, 0, 52)
titleBar.BackgroundColor3 = Color3.fromRGB(13, 13, 13)
titleBar.BorderSizePixel = 0
titleBar.Parent = mainFrame

local titleLogo = Instance.new("ImageLabel")
titleLogo.Size = UDim2.new(0, 34, 0, 34)
titleLogo.Position = UDim2.new(0, 16, 0.5, -17)
titleLogo.BackgroundTransparency = 1
titleLogo.Image = "rbxassetid://319779388"
titleLogo.Parent = titleBar
Instance.new("UICorner", titleLogo).CornerRadius = UDim.new(1, 0)

local titleLabel = Instance.new("TextLabel")
titleLabel.Size = UDim2.new(1, -80, 1, 0)
titleLabel.Position = UDim2.new(0, 62, 0, 0)
titleLabel.BackgroundTransparency = 1
titleLabel.Text = "Project DarkLuaSS v1.0"
titleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
titleLabel.TextSize = 18
titleLabel.Font = Enum.Font.GothamSemibold
titleLabel.TextXAlignment = Enum.TextXAlignment.Left
titleLabel.Parent = titleBar

local closeBtn = Instance.new("TextButton")
closeBtn.Size = UDim2.new(0, 38, 0, 38)
closeBtn.Position = UDim2.new(1, -46, 0.5, -19)
closeBtn.BackgroundTransparency = 1
closeBtn.Text = "×"
closeBtn.TextColor3 = Color3.fromRGB(200, 200, 200)
closeBtn.TextSize = 26
closeBtn.Font = Enum.Font.GothamBold
closeBtn.Parent = titleBar

local scriptBox = Instance.new("TextBox")
scriptBox.Size = UDim2.new(1, -32, 1, -135)
scriptBox.Position = UDim2.new(0, 16, 0, 65)
scriptBox.BackgroundColor3 = Color3.fromRGB(24, 24, 24)
scriptBox.TextColor3 = Color3.fromRGB(215, 215, 215)
scriptBox.PlaceholderText = "Paste your script here..."
scriptBox.Text = ""
scriptBox.TextWrapped = true
scriptBox.TextXAlignment = Enum.TextXAlignment.Left
scriptBox.TextYAlignment = Enum.TextYAlignment.Top
scriptBox.TextSize = 16
scriptBox.Font = Enum.Font.Code
scriptBox.MultiLine = true
scriptBox.ClearTextOnFocus = false
scriptBox.Parent = mainFrame

local btnFrame = Instance.new("Frame")
btnFrame.Size = UDim2.new(1, -32, 0, 52)
btnFrame.Position = UDim2.new(0, 16, 1, -68)
btnFrame.BackgroundTransparency = 1
btnFrame.Parent = mainFrame

local layout = Instance.new("UIListLayout")
layout.FillDirection = Enum.FillDirection.Horizontal
layout.HorizontalAlignment = Enum.HorizontalAlignment.Center
layout.Padding = UDim.new(0, 14)
layout.Parent = btnFrame

local function createButton(text, callback)
	local btn = Instance.new("TextButton")
	btn.Size = UDim2.new(0, 170, 1, 0)
	btn.BackgroundColor3 = Color3.fromRGB(28, 28, 28)
	btn.Text = text
	btn.TextColor3 = Color3.fromRGB(255, 255, 255)
	btn.TextSize = 16
	btn.Font = Enum.Font.GothamSemibold
	btn.Parent = btnFrame
	Instance.new("UIStroke", btn).Color = Color3.fromRGB(55, 55, 55)
	Instance.new("UIStroke", btn).Thickness = 1.5
	btn.MouseButton1Click:Connect(callback)
end

createButton("Execute", function()
	local code = scriptBox.Text
	if code and code:match("%S") then
		pcall(loadstring(code))
	end
end)

createButton("Clear", function()
	scriptBox.Text = ""
end)

createButton("Inject", function()
	local code = scriptBox.Text
	if code and code:match("%S") then
		print("[DarkLuaSS] Injecting...")
		pcall(loadstring(code))
	end
end)

-- Key Kontrol
submitBtn.MouseButton1Click:Connect(function()
	if keyBox.Text == CORRECT_KEY then
		keyFrame:Destroy()
		mainFrame.Visible = true
		
		local logo = Instance.new("ImageLabel")
		logo.Size = UDim2.new(0, 120, 0, 120)
		logo.Position = UDim2.new(0.5, -60, 0.5, -60)
		logo.BackgroundTransparency = 1
		logo.Image = "rbxassetid://319779388"
		logo.Parent = screenGui
		Instance.new("UICorner", logo).CornerRadius = UDim.new(1, 0)

		task.wait(0.2)
		TweenService:Create(logo, TweenInfo.new(1.6, Enum.EasingStyle.Quint, Enum.EasingDirection.Out), {Position = UDim2.new(0, 30, 1, -165)}):Play()
		TweenService:Create(logo, TweenInfo.new(2.3, Enum.EasingStyle.Linear, Enum.EasingDirection.Out, -1), {Rotation = 360}):Play()
		
		print("[DarkLuaSS] Key accepted!")
	else
		submitBtn.Text = "Invalid Key"
		submitBtn.TextColor3 = Color3.fromRGB(255, 80, 80)
		task.wait(2)
		submitBtn.Text = "Submit Key"
		submitBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
	end
end)

-- Sürükleme
local dragging = false
local dragStart, startPos

titleBar.InputBegan:Connect(function(input)
	if input.UserInputType == Enum.UserInputType.MouseButton1 then
		dragging = true
		dragStart = input.Position
		startPos = mainFrame.Position
	end
end)

UserInputService.InputChanged:Connect(function(input)
	if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then
		local delta = input.Position - dragStart
		mainFrame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
	end
end)

UserInputService.InputEnded:Connect(function(input)
	if input.UserInputType == Enum.UserInputType.MouseButton1 then
		dragging = false
	end
end)

closeBtn.MouseButton1Click:Connect(function()
	screenGui:Destroy()
end)

print("Project DarkLuaSS v1.0 loaded - Key: DARKSERVERSİDE")
