local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local backpack = player.Backpack

-- Função para mover o personagem voando para uma posição específica
local function flyToPosition(position)
    local bodyVelocity = Instance.new("BodyVelocity")
    bodyVelocity.Velocity = (position - character.HumanoidRootPart.Position).unit * 50 -- Ajuste a velocidade conforme necessário
    bodyVelocity.Parent = character.HumanoidRootPart

    while (character.HumanoidRootPart.Position - position).magnitude > 5 do
        wait()
    end

    bodyVelocity:Destroy()
    character.HumanoidRootPart.CFrame = CFrame.new(position)
end

-- Opção 1: Mineração Automática
local function mine()
    while true do
        if #backpack:GetChildren() < backpack.MaxItems then
            flyToPosition(Vector3.new(10, 0, 10)) -- Exemplo de posição de mineração
            wait(5) -- Tempo de espera entre as ações
        else
            print("Bolsa cheia!")
            break
        end
    end
end

-- Opção 2: Venda Automática
local function sellItems()
    while true do
        if #backpack:GetChildren() > 0 then
            flyToPosition(Vector3.new(20, 0, 20)) -- Exemplo de posição de venda
            wait(5) -- Tempo de espera entre as ações
        else
            print("Bolsa vazia!")
            break
        end
    end
end

-- Opção 3: Roubo de Banco
local function robBank()
    while true do
        flyToPosition(Vector3.new(30, 0, 30)) -- Exemplo de posição do banco
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 4: Roubo de Caixas Registradoras
local function robCashRegisters()
    while true do
        flyToPosition(Vector3.new(40, 0, 40)) -- Exemplo de posição das caixas registradoras
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 5: Assalto ao Trem
local function robTrain()
    while true do
        flyToPosition(Vector3.new(50, 0, 50)) -- Exemplo de posição do trem
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 6: Caçar Animais Lendários
local function huntLegendaryAnimals()
    while true do
        -- Código para caçar animais lendários
        flyToPosition(Vector3.new(60, 0, 60)) -- Exemplo de posição de animais lendários
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 7: Caçar Animais Não Lendários
local function huntNonLegendaryAnimals()
    while true do
        -- Código para caçar animais não lendários
        flyToPosition(Vector3.new(70, 0, 70)) -- Exemplo de posição de animais não lendários
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Criação da interface do usuário
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local MineButton = Instance.new("TextButton")
local SellButton = Instance.new("TextButton")
local RobBankButton = Instance.new("TextButton")
local RobCashRegistersButton = Instance.new("TextButton")
local RobTrainButton = Instance.new("TextButton")
local HuntLegendaryButton = Instance.new("TextButton")
local HuntNonLegendaryButton = Instance.new("TextButton")

ScreenGui.Parent = player:WaitForChild("PlayerGui")

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.Position = UDim2.new(0.5, -100, 0.5, -200)
Frame.Size = UDim2.new(0, 200, 0, 400)

TextLabel.Parent = Frame
TextLabel.Size = UDim2.new(1, 0, 0, 50)
TextLabel.Text = "Farm Hub"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextScaled = true

MineButton.Parent = Frame
MineButton.Position = UDim2.new(0, 0, 0, 50)
MineButton.Size = UDim2.new(1, 0, 0, 40)
MineButton.Text = "Mineração"
MineButton.MouseButton1Click:Connect(mine)

SellButton.Parent = Frame
SellButton.Position = UDim2.new(0, 0, 0, 100)
SellButton.Size = UDim2.new(1, 0, 0, 40)
SellButton.Text = "Venda"
SellButton.MouseButton1Click:Connect(sellItems)

RobBankButton.Parent = Frame
RobBankButton.Position = UDim2.new(0, 0, 0, 150)
RobBankButton.Size = UDim2.new(1, 0, 0, 40)
RobBankButton.Text = "Roubo de Banco"
RobBankButton.MouseButton1Click:Connect(robBank)

RobCashRegistersButton.Parent = Frame
RobCashRegistersButton.Position = UDim2.new(0, 0, 0, 200)
RobCashRegistersButton.Size = UDim2.new(1, 0, 0, 40)
RobCashRegistersButton.Text = "Roubo de Caixas Registradoras"
RobCashRegistersButton.MouseButton1Click:Connect(robCashRegisters)

RobTrainButton.Parent = Frame
RobTrainButton.Position = UDim2.new(0, 0, 0, 250)
RobTrainButton.Size = UDim2.new(1, 0, 0, 40)
RobTrainButton.Text = "Assalto ao Trem"
RobTrainButton.MouseButton1Click:Connect(robTrain)

HuntLegendaryButton.Parent = Frame
HuntLegendaryButton.Position = UDim2.new(0, 0, 0, 300)
HuntLegendaryButton.Size = UDim2.new(1, 0, 0, 40)
HuntLegendaryButton.Text = "Caçar Animais Lendários"
HuntLegendaryButton.MouseButton1Click:Connect(huntLegendaryAnimals)

HuntNonLegendaryButton.Parent = Frame
HuntNonLegendaryButton.Position = UDim2.new(0, 0, 0, 350)
HuntNonLegendaryButton.Size = UDim2.new(1, 0, 0, 40)
HuntNonLegendaryButton.Text = "Caçar Animais Não Lendários"
HuntNonLegendaryButton.MouseButton1Click:Connect(huntNonLegendaryAnimals)
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local backpack = player.Backpack

-- Função para mover o personagem voando para uma posição específica
local function flyToPosition(position)
    local bodyVelocity = Instance.new("BodyVelocity")
    bodyVelocity.Velocity = (position - character.HumanoidRootPart.Position).unit * 50 -- Ajuste a velocidade conforme necessário
    bodyVelocity.Parent = character.HumanoidRootPart

    while (character.HumanoidRootPart.Position - position).magnitude > 5 do
        wait()
    end

    bodyVelocity:Destroy()
    character.HumanoidRootPart.CFrame = CFrame.new(position)
end

-- Opção 1: Mineração Automática
local function mine()
    while true do
        if #backpack:GetChildren() < backpack.MaxItems then
            flyToPosition(Vector3.new(10, 0, 10)) -- Exemplo de posição de mineração
            wait(5) -- Tempo de espera entre as ações
        else
            print("Bolsa cheia!")
            break
        end
    end
end

-- Opção 2: Venda Automática
local function sellItems()
    while true do
        if #backpack:GetChildren() > 0 then
            flyToPosition(Vector3.new(20, 0, 20)) -- Exemplo de posição de venda
            wait(5) -- Tempo de espera entre as ações
        else
            print("Bolsa vazia!")
            break
        end
    end
end

-- Opção 3: Roubo de Banco
local function robBank()
    while true do
        flyToPosition(Vector3.new(30, 0, 30)) -- Exemplo de posição do banco
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 4: Roubo de Caixas Registradoras
local function robCashRegisters()
    while true do
        flyToPosition(Vector3.new(40, 0, 40)) -- Exemplo de posição das caixas registradoras
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 5: Assalto ao Trem
local function robTrain()
    while true do
        flyToPosition(Vector3.new(50, 0, 50)) -- Exemplo de posição do trem
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 6: Caçar Animais Lendários
local function huntLegendaryAnimals()
    while true do
        -- Código para caçar animais lendários
        flyToPosition(Vector3.new(60, 0, 60)) -- Exemplo de posição de animais lendários
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 7: Caçar Animais Não Lendários
local function huntNonLegendaryAnimals()
    while true do
        -- Código para caçar animais não lendários
        flyToPosition(Vector3.new(70, 0, 70)) -- Exemplo de posição de animais não lendários
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Criação da interface do usuário
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local MineButton = Instance.new("TextButton")
local SellButton = Instance.new("TextButton")
local RobBankButton = Instance.new("TextButton")
local RobCashRegistersButton = Instance.new("TextButton")
local RobTrainButton = Instance.new("TextButton")
local HuntLegendaryButton = Instance.new("TextButton")
local HuntNonLegendaryButton = Instance.new("TextButton")

ScreenGui.Parent = player:WaitForChild("PlayerGui")

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.Position = UDim2.new(0.5, -100, 0.5, -200)
Frame.Size = UDim2.new(0, 200, 0, 400)

TextLabel.Parent = Frame
TextLabel.Size = UDim2.new(1, 0, 0, 50)
TextLabel.Text = "Farm Hub"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextScaled = true

MineButton.Parent = Frame
MineButton.Position = UDim2.new(0, 0, 0, 50)
MineButton.Size = UDim2.new(1, 0, 0, 40)
MineButton.Text = "Mineração"
MineButton.MouseButton1Click:Connect(mine)

SellButton.Parent = Frame
SellButton.Position = UDim2.new(0, 0, 0, 100)
SellButton.Size = UDim2.new(1, 0, 0, 40)
SellButton.Text = "Venda"
SellButton.MouseButton1Click:Connect(sellItems)

RobBankButton.Parent = Frame
RobBankButton.Position = UDim2.new(0, 0, 0, 150)
RobBankButton.Size = UDim2.new(1, 0, 0, 40)
RobBankButton.Text = "Roubo de Banco"
RobBankButton.MouseButton1Click:Connect(robBank)

RobCashRegistersButton.Parent = Frame
RobCashRegistersButton.Position = UDim2.new(0, 0, 0, 200)
RobCashRegistersButton.Size = UDim2.new(1, 0, 0, 40)
RobCashRegistersButton.Text = "Roubo de Caixas Registradoras"
RobCashRegistersButton.MouseButton1Click:Connect(robCashRegisters)

RobTrainButton.Parent = Frame
RobTrainButton.Position = UDim2.new(0, 0, 0, 250)
RobTrainButton.Size = UDim2.new(1, 0, 0, 40)
RobTrainButton.Text = "Assalto ao Trem"
RobTrainButton.MouseButton1Click:Connect(robTrain)

HuntLegendaryButton.Parent = Frame
HuntLegendaryButton.Position = UDim2.new(0, 0, 0, 300)
HuntLegendaryButton.Size = UDim2.new(1, 0, 0, 40)
HuntLegendaryButton.Text = "Caçar Animais Lendários"
HuntLegendaryButton.MouseButton1Click:Connect(huntLegendaryAnimals)

HuntNonLegendaryButton.Parent = Frame
HuntNonLegendaryButton.Position = UDim2.new(0, 0, 0, 350)
HuntNonLegendaryButton.Size = UDim2.new(1, 0, 0, 40)
HuntNonLegendaryButton.Text = "Caçar Animais Não Lendários"
HuntNonLegendaryButton.MouseButton1Click:Connect(huntNonLegendaryAnimals)
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local backpack = player.Backpack

-- Função para mover o personagem voando para uma posição específica
local function flyToPosition(position)
    local bodyVelocity = Instance.new("BodyVelocity")
    bodyVelocity.Velocity = (position - character.HumanoidRootPart.Position).unit * 50 -- Ajuste a velocidade conforme necessário
    bodyVelocity.Parent = character.HumanoidRootPart

    while (character.HumanoidRootPart.Position - position).magnitude > 5 do
        wait()
    end

    bodyVelocity:Destroy()
    character.HumanoidRootPart.CFrame = CFrame.new(position)
end

-- Opção 1: Mineração Automática
local function mine()
    while true do
        if #backpack:GetChildren() < backpack.MaxItems then
            flyToPosition(Vector3.new(10, 0, 10)) -- Exemplo de posição de mineração
            wait(5) -- Tempo de espera entre as ações
        else
            print("Bolsa cheia!")
            break
        end
    end
end

-- Opção 2: Venda Automática
local function sellItems()
    while true do
        if #backpack:GetChildren() > 0 then
            flyToPosition(Vector3.new(20, 0, 20)) -- Exemplo de posição de venda
            wait(5) -- Tempo de espera entre as ações
        else
            print("Bolsa vazia!")
            break
        end
    end
end

-- Opção 3: Roubo de Banco
local function robBank()
    while true do
        flyToPosition(Vector3.new(30, 0, 30)) -- Exemplo de posição do banco
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 4: Roubo de Caixas Registradoras
local function robCashRegisters()
    while true do
        flyToPosition(Vector3.new(40, 0, 40)) -- Exemplo de posição das caixas registradoras
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 5: Assalto ao Trem
local function robTrain()
    while true do
        flyToPosition(Vector3.new(50, 0, 50)) -- Exemplo de posição do trem
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 6: Caçar Animais Lendários
local function huntLegendaryAnimals()
    while true do
        -- Código para caçar animais lendários
        flyToPosition(Vector3.new(60, 0, 60)) -- Exemplo de posição de animais lendários
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 7: Caçar Animais Não Lendários
local function huntNonLegendaryAnimals()
    while true do
        -- Código para caçar animais não lendários
        flyToPosition(Vector3.new(70, 0, 70)) -- Exemplo de posição de animais não lendários
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Criação da interface do usuário
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local MineButton = Instance.new("TextButton")
local SellButton = Instance.new("TextButton")
local RobBankButton = Instance.new("TextButton")
local RobCashRegistersButton = Instance.new("TextButton")
local RobTrainButton = Instance.new("TextButton")
local HuntLegendaryButton = Instance.new("TextButton")
local HuntNonLegendaryButton = Instance.new("TextButton")

ScreenGui.Parent = player:WaitForChild("PlayerGui")

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.Position = UDim2.new(0.5, -100, 0.5, -200)
Frame.Size = UDim2.new(0, 200, 0, 400)

TextLabel.Parent = Frame
TextLabel.Size = UDim2.new(1, 0, 0, 50)
TextLabel.Text = "Farm Hub"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextScaled = true

MineButton.Parent = Frame
MineButton.Position = UDim2.new(0, 0, 0, 50)
MineButton.Size = UDim2.new(1, 0, 0, 40)
MineButton.Text = "Mineração"
MineButton.MouseButton1Click:Connect(mine)

SellButton.Parent = Frame
SellButton.Position = UDim2.new(0, 0, 0, 100)
SellButton.Size = UDim2.new(1, 0, 0, 40)
SellButton.Text = "Venda"
SellButton.MouseButton1Click:Connect(sellItems)

RobBankButton.Parent = Frame
RobBankButton.Position = UDim2.new(0, 0, 0, 150)
RobBankButton.Size = UDim2.new(1, 0, 0, 40)
RobBankButton.Text = "Roubo de Banco"
RobBankButton.MouseButton1Click:Connect(robBank)

RobCashRegistersButton.Parent = Frame
RobCashRegistersButton.Position = UDim2.new(0, 0, 0, 200)
RobCashRegistersButton.Size = UDim2.new(1, 0, 0, 40)
RobCashRegistersButton.Text = "Roubo de Caixas Registradoras"
RobCashRegistersButton.MouseButton1Click:Connect(robCashRegisters)

RobTrainButton.Parent = Frame
RobTrainButton.Position = UDim2.new(0, 0, 0, 250)
RobTrainButton.Size = UDim2.new(1, 0, 0, 40)
RobTrainButton.Text = "Assalto ao Trem"
RobTrainButton.MouseButton1Click:Connect(robTrain)

HuntLegendaryButton.Parent = Frame
HuntLegendaryButton.Position = UDim2.new(0, 0, 0, 300)
HuntLegendaryButton.Size = UDim2.new(1, 0, 0, 40)
HuntLegendaryButton.Text = "Caçar Animais Lendários"
HuntLegendaryButton.MouseButton1Click:Connect(huntLegendaryAnimals)

HuntNonLegendaryButton.Parent = Frame
HuntNonLegendaryButton.Position = UDim2.new(0, 0, 0, 350)
HuntNonLegendaryButton.Size = UDim2.new(1, 0, 0, 40)
HuntNonLegendaryButton.Text = "Caçar Animais Não Lendários"
HuntNonLegendaryButton.MouseButton1Click:Connect(huntNonLegendaryAnimals)
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local backpack = player.Backpack

-- Função para mover o personagem voando para uma posição específica
local function flyToPosition(position)
    local bodyVelocity = Instance.new("BodyVelocity")
    bodyVelocity.Velocity = (position - character.HumanoidRootPart.Position).unit * 50 -- Ajuste a velocidade conforme necessário
    bodyVelocity.Parent = character.HumanoidRootPart

    while (character.HumanoidRootPart.Position - position).magnitude > 5 do
        wait()
    end

    bodyVelocity:Destroy()
    character.HumanoidRootPart.CFrame = CFrame.new(position)
end

-- Opção 1: Mineração Automática
local function mine()
    while true do
        if #backpack:GetChildren() < backpack.MaxItems then
            flyToPosition(Vector3.new(10, 0, 10)) -- Exemplo de posição de mineração
            wait(5) -- Tempo de espera entre as ações
        else
            print("Bolsa cheia!")
            break
        end
    end
end

-- Opção 2: Venda Automática
local function sellItems()
    while true do
        if #backpack:GetChildren() > 0 then
            flyToPosition(Vector3.new(20, 0, 20)) -- Exemplo de posição de venda
            wait(5) -- Tempo de espera entre as ações
        else
            print("Bolsa vazia!")
            break
        end
    end
end

-- Opção 3: Roubo de Banco
local function robBank()
    while true do
        flyToPosition(Vector3.new(30, 0, 30)) -- Exemplo de posição do banco
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 4: Roubo de Caixas Registradoras
local function robCashRegisters()
    while true do
        flyToPosition(Vector3.new(40, 0, 40)) -- Exemplo de posição das caixas registradoras
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 5: Assalto ao Trem
local function robTrain()
    while true do
        flyToPosition(Vector3.new(50, 0, 50)) -- Exemplo de posição do trem
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 6: Caçar Animais Lendários
local function huntLegendaryAnimals()
    while true do
        -- Código para caçar animais lendários
        flyToPosition(Vector3.new(60, 0, 60)) -- Exemplo de posição de animais lendários
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Opção 7: Caçar Animais Não Lendários
local function huntNonLegendaryAnimals()
    while true do
        -- Código para caçar animais não lendários
        flyToPosition(Vector3.new(70, 0, 70)) -- Exemplo de posição de animais não lendários
        wait(5) -- Tempo de espera entre as ações
    end
end

-- Criação da interface do usuário
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local MineButton = Instance.new("TextButton")
local SellButton = Instance.new("TextButton")
local RobBankButton = Instance.new("TextButton")
local RobCashRegistersButton = Instance.new("TextButton")
local RobTrainButton = Instance.new("TextButton")
local HuntLegendaryButton = Instance.new("TextButton")
local HuntNonLegendaryButton = Instance.new("TextButton")

ScreenGui.Parent = player:WaitForChild("PlayerGui")

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.Position = UDim2.new(0.5, -100, 0.5, -200)
Frame.Size = UDim2.new(0, 200, 0, 400)

TextLabel.Parent = Frame
TextLabel.Size = UDim2.new(1, 0, 0, 50)
TextLabel.Text = "Farm Hub"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextScaled = true

MineButton.Parent = Frame
MineButton.Position = UDim2.new(0, 0, 0, 50)
MineButton.Size = UDim2.new(1, 0, 0, 40)
MineButton.Text = "Mineração"
MineButton.MouseButton1Click:Connect(mine)

SellButton.Parent = Frame
SellButton.Position = UDim2.new(0, 0, 0, 100)
SellButton.Size = UDim2.new(1, 0, 0, 40)
SellButton.Text = "Venda"
SellButton.MouseButton1Click:Connect(sellItems)

RobBankButton.Parent = Frame
RobBankButton.Position = UDim2.new(0, 0, 0, 150)
RobBankButton.Size = UDim2.new(1, 0, 0, 40)
RobBankButton.Text = "Roubo de Banco"
RobBankButton.MouseButton1Click:Connect(robBank)

RobCashRegistersButton.Parent = Frame
RobCashRegistersButton.Position = UDim2.new(0, 0, 0, 200)
RobCashRegistersButton.Size = UDim2.new(1, 0, 0, 40)
RobCashRegistersButton.Text = "Roubo de Caixas Registradoras"
RobCashRegistersButton.MouseButton1Click:Connect(robCashRegisters)

RobTrainButton.Parent = Frame
RobTrainButton.Position = UDim2.new(0, 0, 0, 250)
RobTrainButton.Size = UDim2.new(1, 0, 0, 40)
RobTrainButton.Text = "Assalto ao Trem"
RobTrainButton.MouseButton1Click:Connect(robTrain)

HuntLegendaryButton.Parent = Frame
HuntLegendaryButton.Position = UDim2.new(0, 0, 0, 300)
HuntLegendaryButton.Size = UDim2.new(1, 0, 0, 40)
HuntLegendaryButton.Text = "Caçar Animais Lendários"
HuntLegendaryButton.MouseButton1Click:Connect(huntLegendaryAnimals)

HuntNonLegendaryButton.Parent = Frame
HuntNonLegendaryButton.Position = UDim2.new(0, 0, 0, 350)
HuntNonLegendaryButton.Size = UDim2.new(1, 0, 0, 40)
HuntNonLegendaryButton.Text = "Caçar Animais Não Lendários"
HuntNonLegendaryButton.MouseButton1Click:Connect(huntNonLegendaryAnimals)
