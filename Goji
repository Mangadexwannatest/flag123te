local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/4DailRyz/1yrsZHUB/main/kavo%20ui"))()
local Window = Library.CreateLib("TITLE")
local Tab = Window:NewTab("TabName")
local Section = Tab:NewSection("Section Name")

Section:NewToggle("Auto Bounty Hunter", nil, function(bool)
    getgenv().AutoBountyHunter = bool
end)

Section:NewKeybind("Hid Gui", nil, Enum.KeyCode.F, function()
	Library:ToggleUI()
end)


---------------- Auto Bounty Hunter V1 -----------------
task.spawn(function ()
    while task.wait() do pcall(function ()
        if getgenv().AutoBountyHunter and not getgenv().InBossHunt then
            for i,v in pairs(game.Workspace.NPC:GetChildren()) do
                if v.Name == "Kuru" then
                local dist = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.HumanoidRootPart.Position).Magnitude
                if dist >= 30 then
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,3)
                        game.Workspace.NPC.Kuru.HumanoidRootPart.Task.HoldDuration = 0
                else
                        game.Workspace.NPC.Kuru.HumanoidRootPart.Task.HoldDuration = 0
                        game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, nil)
                        game:GetService("VirtualInputManager"):SendKeyEvent(false, "E", false, nil)
                        
                            end
                       end
                    end
               end
        end)
     end
end)

task.spawn(function ()
    while task.wait() do pcall(function ()
        if getgenv().AutoBountyHunter then
        for i,v in pairs(game.Workspace.Lives:GetChildren()) do
            if string.find(v.Name,"Criminal") and v.Humanoid.Health ~= 0  then
                getgenv().InBossHunt = true
                repeat task.wait()
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,4)
                until v.Humanoid.Health == 0 or v.Humanoid.Health < 0 or getgenv().STOP or not getgenv().AutoBountyHunter or game.PlaceId ~= 15049111150
                getgenv().InBossHunt = false
                end
            end
         end
      end)
    end
end)


task.spawn(function ()
    while task.wait() do pcall(function ()
            for i,v in pairs(game.Workspace.Chests:GetDescendants()) do
                if v.Name == "ProximityPrompt" then
                    fireproximityprompt(v)
                end            
             end
         end)  
    end 
end)
