-- ============================================================
-- OZELA Family
-- ============================================================

-- 1. MEMBUAT ANTARMUKA (UI)
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local FrameCorner = Instance.new("UICorner")
local Title = Instance.new("TextLabel")
local SpeedButton = Instance.new("TextButton")
local JumpButton = Instance.new("TextButton")
local InfJumpButton = Instance.new("TextButton")
local ResetButton = Instance.new("TextButton")

-- Mengatur tempat penyimpanan UI agar muncul di layar
ScreenGui.Parent = game:GetService("CoreGui") or game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.Name = "Erenskhigal"

-- [FRAME UTAMA] Menggunakan warna Ultra Dark Charcoal (#121212)
MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(18, 18, 18) -- Gelap pekat namun elegan
MainFrame.Position = UDim2.new(0.05, 0, 0.35, 0)
MainFrame.Size = UDim2.new(0, 200, 0, 240) -- Sedikit lebih luas agar teks tidak padat
MainFrame.Active = true
MainFrame.Draggable = true 

-- Membuat sudut Frame Utama melengkung modern
FrameCorner.CornerRadius = UDim.new(0, 10)
FrameCorner.Parent = MainFrame

-- [JUDUL MENU] Menggunakan font GothamBold yang sangat tegas & jelas
Title.Name = "Zilya"
Title.Parent = MainFrame
Title.BackgroundColor3 = Color3.fromRGB(28, 28, 28) -- Sedikit lebih terang dari background utama
Title.Size = UDim2.new(1, 0, 0, 35)
Title.Font = Enum.Font.GothamBold -- Font modern kelas atas
Title.Text = "DARK ADMIN v1.0"
Title.TextColor3 = Color3.fromRGB(240, 240, 240) -- Putih bersih berkilau
Title.TextSize = 14

-- Membuat sudut judul atas melengkung mengikuti frame
local TitleCorner = Instance.new("UICorner")
TitleCorner.CornerRadius = UDim.new(0, 10)
TitleCorner.Parent = Title

-- FUNGSI OTOMATIS UNTUK TOMBOL (DARK STYLE)
local function buatTombolDark(tombol, nama, teks, posisiY)
    tombol.Name = nama
    tombol.Parent = MainFrame
    tombol.BackgroundColor3 = Color3.fromRGB(33, 33, 33) -- Abu-abu kontras untuk tombol
    tombol.Position = UDim2.new(0.05, 0, 0, posisiY)
    tombol.Size = UDim2.new(0.9, 0, 0, 35)
    tombol.Font = Enum.Font.GothamSemibold -- Huruf tebal medium agar mudah dibaca
    tombol.Text = teks
    tombol.TextColor3 = Color3.fromRGB(225, 225, 225) -- Kontras tinggi dengan latar tombol
    tombol.TextSize = 12
    
    -- Sudut tombol melengkung halus
    local ButtonCorner = Instance.new("UICorner")
    ButtonCorner.CornerRadius = UDim.new(0, 6)
    ButtonCorner.Parent = tombol
    
    -- Efek Interaksi: Berubah warna sedikit terang saat disentuh mouse (Hover)
    tombol.MouseEnter:Connect(function()
        tombol.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
    end)
    tombol.MouseLeave:Connect(function()
        tombol.BackgroundColor3 = Color3.fromRGB(33, 33, 33)
    end)
end

-- Menata posisi tombol dengan jarak (padding) yang pas agar tidak berdempetan
buatTombolDark(SpeedButton, "SpeedButton", "Lari Cepat (Speed 100)", 50)
buatTombolDark(JumpButton, "JumpButton", "Lompat Tinggi (JP 120)", 95)
buatTombolDark(InfJumpButton, "InfJumpButton", "Infinite Jump: OFF", 140)
buatTombolDark(ResetButton, "ResetButton", "Kembalikan Normal", 185)


-- ============================================================
-- 2. LOGIKA & FUNGSI FITUR
-- ============================================================

local player = game.Players.LocalPlayer
local infJumpAktif = false

SpeedButton.MouseButton1Click:Connect(function()
    local char = player.Character
    if char and char:FindFirstChildOfClass("Humanoid") then
        char:FindFirstChildOfClass("Humanoid").WalkSpeed = 100
    end
end)

JumpButton.MouseButton1Click:Connect(function()
    local char = player.Character
    if char and char:FindFirstChildOfClass("Humanoid") then
        local hum = char:FindFirstChildOfClass("Humanoid")
        hum.JumpPower = 120
        hum.UseJumpPower = true
    end
end)

InfJumpButton.MouseButton1Click:Connect(function()
    infJumpAktif = not infJumpAktif
    if infJumpAktif then
        InfJumpButton.Text = "Infinite Jump: ON"
        -- Warna hijau gelap yang tetap menyatu dengan tema dark
        InfJumpButton.BackgroundColor3 = Color3.fromRGB(25, 110, 40) 
    else
        InfJumpButton.Text = "Infinite Jump: OFF"
        InfJumpButton.BackgroundColor3 = Color3.fromRGB(33, 33, 33)
    end
end)

game:GetService("UserInputService").JumpRequest:Connect(function()
    if infJumpAktif then
        local char = player.Character
        if char and char:FindFirstChildOfClass("Humanoid") then
            char:FindFirstChildOfClass("Humanoid"):ChangeState("Jumping")
        end
    end
end)

ResetButton.MouseButton1Click:Connect(function()
    local char = player.Character
    if char and char:FindFirstChildOfClass("Humanoid") then
        local hum = char:FindFirstChildOfClass("Humanoid")
        hum.WalkSpeed = 16
        hum.JumpPower = 50
        infJumpAktif = false
        InfJumpButton.Text = "Infinite Jump: OFF"
        InfJumpButton.BackgroundColor3 = Color3.fromRGB(33, 33, 33)
    end
end)

-- Notifikasi dengan gaya gelap bawaan Roblox
game:GetService("StarterGui"):SetCore("SendNotification", {
    Title = "Premium Dark UI";
    Text = "Skrip Berhasil Dimuat!";
    Duration = 4;
})
