task.spawn(function ()
    while task.wait() do pcall(function ()
        if getgenv().AutoBountyHunter and not getgenv().InBossHunt then
            for i,v in pairs(game.Workspace.NPC:GetChildren()) do
                if v.Name == "Kuru" then
                local dist = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.HumanoidRootPart.Position).Magnitude
                if dist >= 30 then
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,3)
                            end
                       end
                    end
               end
        end)
     end
end)

task.spawn(function ()
    while task.wait() do pcall(function ()
        if getgenv().AutoBountyHunter() then
            fireproximityprompt(game.Workspace.NPC.Kuru.HumanoidRootPart.Task)
            wait(.35)
            fireproximityprompt(game.Workspace.NPC.Kuru.HumanoidRootPart.Task)
        end
     end)
    end
end)

task.spawn(function ()
    while task.wait() do pcall(function ()
        if getgenv().AutoBountyHunter then
        for i,v in pairs(game.Workspace.Lives:GetChildren()) do
            if string.find(v.Name,"Criminal") and v.Humanoid.Health ~= 0  then
                repeat task.wait()
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,4)
                    getgenv().InBossHunt = true
                until v.Humanoid.Health == 0 or v.Humanoid.Health < 0 or getgenv().STOP or not getgenv().AutoBountyHunter or game.PlaceId ~= 15049111150
                or game.Workspace.Lives:FindFirstChild(v) == nil
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
