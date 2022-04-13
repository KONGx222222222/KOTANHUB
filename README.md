function CheckQuest()
        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
            if Lv == 1 or Lv <= 9 then
                Mon = "Bandit [Lv. 5]"
                NameMon = "Bandit"
                LvQuest = 1
                NameQuest = "BanditQuest1"
                CFrameMon = CFrame.new(1038.2711181640625, 24.537282943725586, 1550.2586669921875)
                CFrameQuest = CFrame.new(1059.8109130859375, 16.362747192382812, 1549.0882568359375)
            elseif Lv == 10 or Lv <= 14 then
                Mon = "Monkey [Lv. 14]"
                NameMon = "Monkey"
                LvQuest = 1
                NameQuest = "JungleQuest"
                CFrameMon = CFrame.new(-1443.7662353515625, 61.851966857910156, -47.555946350097656)
                CFrameQuest = CFrame.new(-1599.8194580078125, 36.852149963378906, 153.0706024169922)
                elseif Lv == 15 or Lv <= 29 then
                Mon = "Gorilla [Lv. 20]"
                NameMon = "Gorilla"
                LvQuest = 2
                NameQuest = "JungleQuest"
                CFrameMon = CFrame.new(-1443.7662353515625, 61.851966857910156, -47.555946350097656)
                CFrameQuest = CFrame.new(-1599.8194580078125, 36.852149963378906, 153.0706024169922) 
            elseif Lv == 30 or Lv <= 44 then
                Mon = "Pirate [Lv. 35]"
                NameMon = "Pirate"
                LvQuest = 1
                NameQuest = "PirateQuest"
                CFrameMon = CFrame.new(1216.17969, 4.75206137, 3913.11938, -0.260275573, 0, 0.965534449, 0, 1.00000012, -0, -0.965534449, 0, -0.260275573)
                CFrameQuest = CFrame.new(-1171.38159, 4.75206137, 3830.69678, 0.825265348, 0, -0.564745188, -0, 1, -0, 0.564745188, 0, 0.825265348)
             elseif Lv == 45 or Lv <= 59 then
                Mon = "Brutes [Lv. 45]"
                NameMon = "Brutes"
                LvQuest = 2
                NameQuest = "PirateQuest"
                CFrameMon = CFrame.new(-1150.29675, 14.809885, 4306.65381, -0.895984232, 0, 0.444085926, 0, 1, -0, -0.444085926, 0, -0.895984232)
                CFrameQuest = CFrame.new(-1171.38159, 4.75206137, 3830.69678, 0.825265348, 0, -0.564745188, -0, 1, -0, 0.564745188, 0, 0.825265348)
             elseif Lv == 60 or Lv <= 74 then
                Mon = "Desert bandit [Lv. 60]"
                NameMon = "Desert bandit"
                LvQuest = 1
                NameQuest = "DesertQuest"
                CFrameMon = CFrame.new(940.496582, 13.5789442, 4475.69482, -0.822328448, 0, 0.569013178, 0, 1, -0, -0.569013178, 0, -0.822328448)
                CFrameQuest = CFrame.new(912.387085, 2.7164309, 4355.9834, 1.2755394e-05, 0.965938866, -0.258770198, -0.99999994, 1.2755394e-05, -1.66893005e-06, 1.66893005e-06, 0.258770198, 0.965938926)
             elseif Lv == 75 or Lv <= 89 then
                Mon = "Desert officer [Lv. 75]"
                NameMon = "Desert office"
                LvQuest = 2
                NameQuest = "DesertQuest"
                CFrameMon = CFrame.new(1608.64429, 9.89187813, 4371.76172, 0.283743531, -1.07372857e-08, -0.958900213, -1.16193801e-08, 1, -1.46357353e-08, 0.958900213, 1.52946207e-08, 0.283743531)
                CFrameQuest = CFrame.new(912.387085, 2.7164309, 4355.9834, 1.2755394e-05, 0.965938866, -0.258770198, -0.99999994, 1.2755394e-05, -1.66893005e-06, 1.66893005e-06, 0.258770198, 0.965938926)
        end 
    end
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/naypramx/Ui__Project/Script/XeNonUi", true))()
    library:CreateWatermark("KOTAN HUB") -- Config แตกนะเดียวค่อยแก้รอเน็ตมาก่อน By MeowX#0001
    local CenterHubNo1 = library:CreateWindow("KOTAN HUB | BETAVERSION",Enum.KeyCode.RightControl)
    local Tab = CenterHubNo1:CreateTab("Main")
    local AutoFarm = Tab:CreateSector("AutoFarm","Left")
    AutoFarm:AddLabel("AutoFarm Lv")
    Weapon = {}
    for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
        if v:IsA"Tool" then
            table.insert(Weapon,v.Name)
    end
end
    local WE = AutoFarm:AddDropdown("Select Weapon",Weapon,"Select Weapon",false,function(t)
        _G.SelectWeapon = t
    end)
function Equip(ToolX)
    if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(ToolX) then
        getgenv().Tol = game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(ToolX)
        game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tol)
    end
end
function click()
   game:GetService'VirtualUser':CaptureController()
   game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
end
 function TP(P)
   local Distance = (P.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude -- จุดที่จะไป Position Only
   local Speed = 300 -- ความเร็วของมึง
   tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear)
   tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = P})
   tween:Play()
 end
         AutoFarm:AddButton("ReSet Weapon",function()
        table.clear(Weapon)
        for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
        if v:IsA"Tool" then
        WE:Add(v.Name)
        end
    end
end)
    AutoFarm:AddToggle("AutoFarm",false,function(t)
        _G.AutoFarm = t
    end)
    AutoFarm:AddToggle("AutoNewworld",false,function(t)
        _G.AutoNewworld = t
    end)
local Stats = Tab:CreateSector("Stats","Reft")
Stats:AddLabel("Stats")
Stats:AddToggle("Auto Melee",false,function(t)
_G.Melee = t
while _G.Melee do wait(.1)
pcall(function()
game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",Point)
end)
end
end)
Stats:AddToggle("Auto Defense",false,function(t)
_G.Defense = t
while _G.Defense do wait(.1)
pcall(function()
game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Defense",Point)
end)
end
end)
Stats:AddToggle("Auto Sword",false,function(t)
_G.Sword = t
while _G.Sword do wait(.1)
pcall(function()
game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Sword",Point)
end)
end
end)
Stats:AddToggle("Auto Gun",false,function(t)
_G.Gun = t
while _G.Gun do wait(.1)
pcall(function()
game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Gun",Point)
end)
end
end)
Stats:AddToggle("Auto Blox Fruit",false,function(t)
_G.Fruit = t
while _G.Fruit do wait(.1)
pcall(function()
game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Demon Fruit",Point)
end)
end
end)
Stats:AddSlider("Point",1,1,100,1,function(x)
Point = x
end)

    spawn(function()
    while wait() do
        if _G.BringMob then
            pcall(function()
            CheckQuest()
       for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
for x,y in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
if v.Name == Mon then
    if y.Name == Mon then
   v.HumanoidRootPart.CFrame = y.HumanoidRootPart.CFrame
   v.HumanoidRootPart.Size = Vector3.new(60,60,60)
   y.HumanoidRootPart.Size = Vector3.new(60,60,60)
   v.HumanoidRootPart.Transparency = 1
   v.HumanoidRootPart.CanCollide = false
   y.HumanoidRootPart.CanCollide = false
   v.Humanoid.WalkSpeed = 0
   y.Humanoid.WalkSpeed = 0
   v.Humanoid.JumpPower = 0
   y.Humanoid.JumpPower = 0
   if sethiddenproperty then
     sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
end
end
end
end
end
end)
end
end
end)


spawn(function()
    while wait() do
        if _G.AutoFarm then
            pcall(function()
            CheckQuest()
    if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
    TP(CFrameQuest)
    if (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5 then
    wait(.1)
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,LvQuest)
    end
    elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
        if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,NameMon) then
            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                if v.Name == Mon and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid")   then
                    if v.Humanoid.Health > 0 then
                    repeat wait()
                        click()
                        Equip(_G.SelectWeapon)
                        HealthMin = v.Humanoid.MaxHealth * 90 / 100
                        Magma = (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
                        if Magma <= 230 then
                            if v.Humanoid.Health > HealthMin then
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,14)
                                else
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,15,0)
                            end
                        end
                            if v.Humanoid.Health > HealthMin then
                        Distance = (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude 
                        Speed = 300 
                        tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear)
                        tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,14)})
                        tween:Play() 
                        else
                        Distance = (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude 
                        Speed = 300 
                        tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear)
                        tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,15,0)})
                        tween:Play()
                            end
                        v.HumanoidRootPart.Size = Vector3.new(60,60,60)
                        v.HumanoidRootPart.CanCaillde = false
                    until _G.AutoFarm == false or v.Humanoid.Health <= 0
                    else
                        TP(CFrameMon)
                    end
                    if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,NameMon) then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                    end
                    if game.Players.LocalPlayer.Character.Humanoid.Health <= 0 then
                        _G.AutoFarm = false
                        wait(3)
                        _G.AutoFarm = true
                        end
                end
                end
        end
        end
       end)
end
end
end)

    local Tab = CenterHubNo1:CreateTab("Teleport")
    local AutoFarm = Tab:CreateSector("World1","Left")
    AutoFarm:AddToggle("Jungle",false,function(t)
        _G.Jungle = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(-1255.14795, 11.8520546, 349.906677, -0.173624292, 0, 0.984811962, 0, 1, 0, -0.984811962, 0, -0.173624292)}):Play()
    end)
    AutoFarm:AddToggle("PirateVillage",false,function(t)
        _G.PirateVillage = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(-1120.14856, 4.75206137, 3855.31763, 0.965929627, 0, -0.258804798, 0, 1, 0, 0.258804798, 0, 0.965929627)}):Play()
    end)

    AutoFarm:AddToggle("Desert",false,function(t)
        _G.Desert = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(974.706848, 6.43895054, 4141.79443, 0.997214317, 3.58546215e-09, 0.0745893791, -3.3013452e-09, 1, -3.93237576e-09, -0.0745893791, 3.67517639e-09, 0.997214317)}):Play()
    end)
    AutoFarm:AddToggle("FrozenVillage",false,function(t)
        _G.FrozenVillage = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(1185.63379, 7.30345106, -1143.36987, -0.484826177, 0, 0.874610543, 0, 1, 0, -0.874610543, 0, -0.484826177)}):Play()
    end)
    AutoFarm:AddToggle("MarineFord2",false,function(t)
        _G.MarineFord2 = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(-4697.32324, 20.6524944, 3975.07129, -0.0175019484, 0, 0.999846816, 0, 1, 0, -0.999846816, 0, -0.0175019484)}):Play()
    end)
    AutoFarm:AddToggle("Skyland1",false,function(t)
        _G.Skyland1 = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(-4857.23584, 717.662598, -2706.27271, -0.866007328, 0, -0.500031352, 0, 1, 0, 0.500031352, 0, -0.866007328)}):Play()
    end)
    AutoFarm:AddToggle("Colosseum",false,function(t)
        _G.Colosseum = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(-1332.94006, 7.28908348, -2896.56055, -0.66911, 0, 0.743163407, 0, 1, 0, -0.743163407, 0, -0.66911)}):Play()
    end)
    AutoFarm:AddToggle("Prison",false,function(t)
        _G.Prison = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(23, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(5047.64453, 3.5282948, 744.748047, 0.117047988, -6.33475921e-08, -0.993126273, -5.4579484e-08, 1, -7.02186753e-08, 0.993126273, 6.24232754e-08, 0.117047988)}):Play()
    end)
    AutoFarm:AddToggle("leaderisland",false,function(t)
        _G.leaderisland = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(-2855.36646, 43.9276657, 5369.2041, 0.936702907, -4.2886743e-08, -0.350125164, 6.30701891e-08, 1, 4.6244292e-08, 0.350125164, -6.53996253e-08, 0.936702907)}):Play()
    end)
    AutoFarm:AddToggle("MagmaVillage",false,function(t)
        _G.MagmaVillage = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(-5193.35498, 8.59068489, 8569.56348, 0.951068401, 0, 0.308980465, 0, 1, 0, -0.308980465, 0, 0.951068401)}):Play()
    end)
    AutoFarm:AddToggle("Fishman",false,function(t)
        _G.Fishman = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(4055.21069, 1.98687148, -1799.82031, -0.135936305, 8.3375113e-08, -0.99071759, -1.51182303e-13, 1, 8.41563121e-08, 0.99071759, 1.14400471e-08, -0.135936305)}):Play()
    end)
    AutoFarm:AddToggle("Waterseven",false,function(t)
        _G.Waterseven = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(5091.09619, 1.50130093, 4033.5708, 0.829036415, 0, 0.559194624, 0, 1, 0, -0.559194624, 0, 0.829036415)}):Play()
    end)
    AutoFarm:AddToggle("Beginnertown",false,function(t)
        _G.Beginnertown = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(1027.58875, 16.4155064, 1367.28564, -0.987685978, 0, -0.156449527, 0, 1, 0, 0.156449527, 0, -0.987685978)}):Play()
    end)
    AutoFarm:AddToggle("Middletown",false,function(t)
        _G.Middletown = t
local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(17, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0),
{CFrame = CFrame.new(-659.096497, 7.85225534, 1583.67395, 0.645720601, 0, 0.763573766, -0, 1, -0, -0.763573766, 0, 0.645720601)}):Play()
    end)


