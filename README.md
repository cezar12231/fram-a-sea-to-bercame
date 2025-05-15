local ScreenGui = Instance.new("ScreenGui", game.Players.LocalPlayer:WaitForChild("PlayerGui"))
local Frame = Instance.new("Frame", ScreenGui)
local TextBox = Instance.new("TextBox", Frame)
local Button = Instance.new("TextButton", Frame)
local CreditLabel = Instance.new("TextLabel", Frame)
local CreditImage = Instance.new("ImageLabel", Frame)

ScreenGui.Name = "MoneyGui"
ScreenGui.ResetOnSpawn = false

Frame.Size = UDim2.new(0, 250, 0, 160)
Frame.Position = UDim2.new(0.5, -125, 0.5, -80)
Frame.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
Frame.Active = true
Frame.Draggable = true

TextBox.PlaceholderText = "Digite a quantia de dinheiro"
TextBox.Size = UDim2.new(1, -20, 0, 40)
TextBox.Position = UDim2.new(0, 10, 0, 10)
TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextBox.TextColor3 = Color3.new(0, 0, 0)
TextBox.Text = ""

Button.Text = "Adicionar dinheiro"
Button.Size = UDim2.new(1, -20, 0, 40)
Button.Position = UDim2.new(0, 10, 0, 60)
Button.BackgroundColor3 = Color3.fromRGB(0, 170, 0)
Button.TextColor3 = Color3.new(1, 1, 1)

-- Imagem do lado do texto "Ajustado por Cezar"
CreditImage.Size = UDim2.new(0, 20, 0, 20)
CreditImage.Position = UDim2.new(0, 10, 1, -25)
CreditImage.BackgroundTransparency = 1
CreditImage.Image = "rbxassetid://116904249789195" -- <--- substitua pelo ID real do decal

CreditLabel.Text = "Ajustado por Cezar"
CreditLabel.Size = UDim2.new(1, -40, 0, 20)
CreditLabel.Position = UDim2.new(0, 35, 1, -25)
CreditLabel.BackgroundTransparency = 1
CreditLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
CreditLabel.TextScaled = true
CreditLabel.Font = Enum.Font.SourceSansItalic
CreditLabel.TextXAlignment = Enum.TextXAlignment.Left

-- Script ajustado por Cezar
Button.MouseButton1Click:Connect(function()
    local desejado = tonumber(TextBox.Text)
    if not desejado then return end

    local valor = desejado / 5

    local args = {
        [1] = "\232\180\173\228\185\176\231\167\141\229\173\144",
        [2] = {
            [1] = 6000001,
            [2] = valor
        }
    }

    game:GetService("ReplicatedStorage").Msg.RemoteFunction:InvokeServer(unpack(args))
end)
