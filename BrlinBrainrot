-- ═══════════════════════════════════════════════
--   🧠 Brlin Funny Gamer — Steal a Brainrot 🧠
--   النسخة الكاملة v1.0
-- ═══════════════════════════════════════════════

local player = game.Players.LocalPlayer

-- دالة جلب الشخصية بأمان
local function getHumanoid()
    local char = player.Character or player.CharacterAdded:Wait()
    return char:WaitForChild("Humanoid")
end

-- دالة جلب جذر الجسد
local function getRoot()
    local char = player.Character or player.CharacterAdded:Wait()
    return char:WaitForChild("HumanoidRootPart")
end

--------------------------------------------------------------------
-- تدمير أي لوحة قديمة (لمنع التكرار عند إعادة التنفيذ!)
--------------------------------------------------------------------
if game.CoreGui:FindFirstChild("BrlinGui") then
    game.CoreGui:FindFirstChild("BrlinGui"):Destroy()
end

--------------------------------------------------------------------
-- بناء الواجهة
--------------------------------------------------------------------
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "BrlinGui"
ScreenGui.ResetOnSpawn = false
ScreenGui.Parent = game.CoreGui

local Frame = Instance.new("Frame")
Frame.Size = UDim2.new(0, 220, 0, 230)
Frame.Position = UDim2.new(0, 20, 0, 200)
Frame.BackgroundColor3 = Color3.fromRGB(25, 25, 35)
Frame.Active = true
Frame.Draggable = true
Frame.Parent = ScreenGui

local Title = Instance.new("TextLabel")
Title.Size = UDim2.new(1, 0, 0, 35)
Title.Text = "🧠 Brlin Funny Gamer 🧠"
Title.TextColor3 = Color3.fromRGB(0, 255, 127)
Title.BackgroundTransparency = 1
Title.TextSize = 15
Title.Parent = Frame

local function makeButton(text, yPos, callback)
    local btn = Instance.new("TextButton")
    btn.Size = UDim2.new(1, -16, 0, 38)
    btn.Position = UDim2.new(0, 8, 0, yPos)
    btn.Text = text
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    btn.BackgroundColor3 = Color3.fromRGB(45, 45, 60)
    btn.TextSize = 14
    btn.Parent = Frame

    local on = false
    btn.MouseButton1Click:Connect(function()
        on = not on
        btn.BackgroundColor3 = on and Color3.fromRGB(0, 150, 70) or Color3.fromRGB(45, 45, 60)
        callback(on)
    end)
end

--------------------------------------------------------------------
-- الهكات
--------------------------------------------------------------------

-- ١. السرعة
makeButton("⚡ Speed Hack [OFF]", 40, function(on)
    local hum = getHumanoid()
    hum.WalkSpeed = on and 100 or 16
end)

-- ٢. القفز العالي
makeButton("🦘 Jump Hack [OFF]", 85, function(on)
    local hum = getHumanoid()
    hum.JumpPower = on and 150 or 50
end)

-- ٣. الإضاءة الليلية (شوف كل شيء!)
makeButton("💡 Full Bright [OFF]", 130, function(on)
    local light = game.Lighting
    if on then
        light.Brightness = 5
        light.ClockTime = 14
        light.FogEnd = 100000
        light.Ambient = Color3.fromRGB(200, 200, 200)
    else
        light.Brightness = 1
        light.ClockTime = 0
        light.FogEnd = 1000
        light.Ambient = Color3.fromRGB(70, 70, 70)
    end
end)

-- ٤. زر التجربة (يرفعك لأعلى!)
makeButton("🚀 Test Launch", 175, function(on)
    local root = getRoot()
    local bv = Instance.new("BodyVelocity")
    bv.MaxForce = Vector3.new(1e9, 1e9, 1e9)
    bv.Velocity = Vector3.new(0, 150, 0)
    bv.Parent = root
    game.Debris:AddItem(bv, 0.3)
end)

--------------------------------------------------------------------
-- إشعار النجاح
--------------------------------------------------------------------
game.StarterGui:SetCore("SendNotification", {
    Title = "🧠 Brlin Funny Gamer",
    Text = "Loaded Successfully ✅",
    Duration = 5
})

print("🧠 Brlin Starter Loaded! ✅")
