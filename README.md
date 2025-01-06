-- UpperCut 💬🔥🔥
-- Local Script put inside Button 📝
-- Made by potato dev 😎👍
-- Like and Subscribe 🥳🥳🥳



local button = script.Parent
local animationId = "rbxassetid://183412246" -- Animation, you can use ur own Animation too 📝
local animationSpeed = 4 -- Animation speed 📝 ye you can changing it
 
local punchEvent = game.ReplicatedStorage:WaitForChild("PunchEvent")
 
local function playAnimation()
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoid = character:FindFirstChildOfClass("Humanoid")
    
    if humanoid then
        local animator = humanoid:FindFirstChildOfClass("Animator") or humanoid:WaitForChild("Animator")
        local animation = Instance.new("Animation")
        animation.AnimationId = animationId
        
        local animationTrack = animator:LoadAnimation(animation)
        animationTrack:Play()
        animationTrack:AdjustSpeed(animationSpeed)
        
        
        punchEvent:FireServer(10, false, true) 
    end
end
 
button.MouseButton1Click:Connect(playAnimation)
