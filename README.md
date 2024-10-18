-- OP Auto Parry Feature
function AutoParry()
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()

    -- Continuously check for incoming attacks
    while true do
        -- Detect incoming attacks
        for _, enemy in pairs(game.Workspace.Enemies:GetChildren()) do
            local distance = (enemy.Position - character.Position).Magnitude
            if distance < 15 then -- Adjust this number for optimal parry range (start with 15)
                -- Call the parry function (replace with actual parry call)
                game.ReplicatedStorage.ParryFunction:FireServer()
            end
        end
    end
end

-- OP Spam Attack Feature
function OPSpamAttack()
    local player = game.Players.LocalPlayer

    -- Continuously spam attack with no delay
    while true do
        -- Trigger the attack (replace with actual attack function)
        game.ReplicatedStorage.AttackFunction:FireServer()
    end
end

-- Load the script
AutoParry()
OPSpamAttack()
