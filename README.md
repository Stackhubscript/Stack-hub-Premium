-- Stack Hub - Super Pulo e Super Velocidade Atualizados
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

-- Espera o personagem carregar
local function getHumanoid()
	local char = LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait()
	return char:WaitForChild("Humanoid")
end

-- Interface
local screenGui = Instance.new("ScreenGui", LocalPlayer:WaitForChild("PlayerGui"))
screenGui.Name = "StackHub"

local mainFrame = Instance.new("Frame", screenGui)
mainFrame.Position = UDim2.new(0.35, 0, 0.25, 0)
mainFrame.Size = UDim2.new(0, 250, 0, 180)
mainFrame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
mainFrame.BorderSizePixel = 2
mainFrame.Name = "StackMain"

local title = Instance.new("TextLabel", mainFrame)
title.Text = "STACK HUB"
title.Font = Enum.Font.Code
title.TextSize = 22
title.TextColor3 = Color3.fromRGB(255, 0, 0)
title.Size = UDim2.new(1, 0, 0, 30)
title.BackgroundTransparency = 1

-- Botão Super Pulo (JumpPower 110)
local jumpButton = Instance.new("TextButton", mainFrame)
jumpButton.Text = "Super Jump"
jumpButton.Font = Enum.Font.Code
jumpButton.TextSize = 18
jumpButton.Size = UDim2.new(0.8, 0, 0, 40)
jumpButton.Position = UDim2.new(0.1, 0, 0.4, 0)
jumpButton.BackgroundColor3 = Color3.fromRGB(60, 0, 0)
jumpButton.TextColor3 = Color3.fromRGB(255, 120, 120)

jumpButton.MouseButton1Click:Connect(function()
	local humanoid = getHumanoid()
	if humanoid then
		humanoid.UseJumpPower = true
		humanoid.JumpPower = 110
		humanoid.Jump = true
	end
end)

-- Botão Super Velocidade (WalkSpeed 200)
local speedButton = Instance.new("TextButton", mainFrame)
speedButton.Text = "Super Speed"
speedButton.Font = Enum.Font.Code
speedButton.TextSize = 18
speedButton.Size = UDim2.new(0.8, 0, 0, 40)
speedButton.Position = UDim2.new(0.1, 0, 0.7, 0)
speedButton.BackgroundColor3 = Color3.fromRGB(60, 0, 0)
speedButton.TextColor3 = Color3.fromRGB(255, 120, 120)

speedButton.MouseButton1Click:Connect(function()
	local humanoid = getHumanoid()
	if humanoid then
		humanoid.WalkSpeed = 200
	end
end)
