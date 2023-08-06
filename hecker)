button={}
function button.new(buttonText,Callback)
    local Button = Instance.new("ScreenGui")
    local Drag = Instance.new("ImageLabel")
    local MAIN = Instance.new("ImageLabel")
    local Button_2 = Instance.new("TextButton")
    local ButtonRound = Instance.new("ImageLabel")
    local DragBg = Instance.new("ImageLabel")

    Button.Name = "Button"..tostring(math.random(0,2500))
    Button.Parent = game.CoreGui
    
    Drag.Name = "Drag"
    Drag.Parent = Button
    Drag.AnchorPoint = Vector2.new(0.5, 0.5)
    Drag.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    Drag.BackgroundTransparency = 1.000
    Drag.Position = UDim2.new(0.5, 0, 0.5, 0)
    Drag.Size = UDim2.new(0, 114, 0, 6)
    Drag.ZIndex = 2
    Drag.Image = "rbxassetid://3570695787"
    Drag.ImageColor3 = Color3.fromRGB(89, 89, 89)
    Drag.ScaleType = Enum.ScaleType.Slice
    Drag.SliceCenter = Rect.new(100, 100, 100, 100)
    Drag.SliceScale = 0.100
    
    MAIN.Name = "MAIN"
    MAIN.Parent = Drag
    MAIN.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    MAIN.BackgroundTransparency = 1.000
    MAIN.Position = UDim2.new(-0.00511947274, 0, 1.39999998, 0)
    MAIN.Size = UDim2.new(0, 114, 0, 39)
    MAIN.ZIndex = 0
    MAIN.Image = "rbxassetid://3570695787"
    MAIN.ImageColor3 = Color3.fromRGB(20, 20, 20)
    MAIN.ScaleType = Enum.ScaleType.Slice
    MAIN.SliceCenter = Rect.new(100, 100, 100, 100)
    MAIN.SliceScale = 0.100
    
    Button_2.Name = "Button"
    Button_2.Parent = MAIN
    Button_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    Button_2.BackgroundTransparency = 1.000
    Button_2.BorderSizePixel = 0
    Button_2.Position = UDim2.new(0.0580861941, 0, 0.0752136931, 0)
    Button_2.Size = UDim2.new(0, 101, 0, 32)
    Button_2.ZIndex = 2
    Button_2.Font = Enum.Font.SourceSansBold
    Button_2.Text = tostring(buttonText)
    Button_2.TextColor3 = Color3.fromRGB(179, 179, 179)
    Button_2.TextScaled = true
    Button_2.TextSize = 23.000
    Button_2.TextWrapped = true
    Button_2.MouseButton1Click:Connect(function()
        ({Callback})[1]()
    end)
    
    ButtonRound.Name = "ButtonRound"
    ButtonRound.Parent = Button_2
    ButtonRound.Active = true
    ButtonRound.AnchorPoint = Vector2.new(0.5, 0.5)
    ButtonRound.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    ButtonRound.BackgroundTransparency = 1.000
    ButtonRound.Position = UDim2.new(0.5, 0, 0.5, 0)
    ButtonRound.Selectable = true
    ButtonRound.Size = UDim2.new(1, 0, 1, 0)
    ButtonRound.Image = "rbxassetid://3570695787"
    ButtonRound.ImageColor3 = Color3.fromRGB(52, 52, 52)
    ButtonRound.ScaleType = Enum.ScaleType.Slice
    ButtonRound.SliceCenter = Rect.new(100, 100, 100, 100)
    ButtonRound.SliceScale = 0.070
    
    DragBg.Name = "DragBg"
    DragBg.Parent = MAIN
    DragBg.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    DragBg.BackgroundTransparency = 1.000
    DragBg.Position = UDim2.new(-0.0550526418, 0, -0.321944803, 0)
    DragBg.Size = UDim2.new(0, 127, 0, 56)
    DragBg.ZIndex = -1
    DragBg.Image = "rbxassetid://3570695787"
    DragBg.ImageColor3 = Color3.fromRGB(7, 7, 7)
    DragBg.ScaleType = Enum.ScaleType.Slice
    DragBg.SliceCenter = Rect.new(100, 100, 100, 100)
    DragBg.SliceScale = 0.100
    --------------
    local UserInputService = game:GetService("UserInputService")
    local gui = Drag
    local dragging
    local dragInput
    local dragStart
    local startPos
    local function update(input)
        local delta = input.Position - dragStart
        gui:TweenPosition(UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y), Enum.EasingDirection.InOut, Enum.EasingStyle.Sine, 0.04, true) -- This is what I changed
    end
    gui.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
            dragging = true
            dragStart = input.Position
            startPos = gui.Position
    
            input.Changed:Connect(function()
                if input.UserInputState == Enum.UserInputState.End then
                    dragging = false
                end
            end)
        end
    end)
    gui.InputChanged:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
            dragInput = input
        end
    end)
    UserInputService.InputChanged:Connect(function(input)
        if input == dragInput and dragging then
            update(input)
        end
    end) 
end
return button
