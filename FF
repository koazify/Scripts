function setupFlingMechanics()
    local humanoidRootPart = playerCharacter:WaitForChild("HumanoidRootPart")
    local humanoid = playerCharacter:WaitForChild("Humanoid")
    
    workspace.ChildAdded:Connect(function(model)
        if model.Name == "GrabParts" then
            local grabPart = model["GrabPart"]["WeldConstraint"].Part1
            
            if grabPart then
                model:GetPropertyChangedSignal("Parent"):Connect(function()
                    if not model.Parent and isFlingEnabled then
                        userInputService.InputBegan:Connect(function(input, chat)
                            if input.UserInputType == Enum.UserInputType.MouseButton2 then
                                local bodyVelocity = Instance.new("BodyVelocity", grabPart)
                                bodyVelocity.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
                                bodyVelocity.Velocity = camera.CFrame.lookVector * flingStrengthValue
                                debrisService:AddItem(bodyVelocity, 1)
                            end
                        end)
                    end
                end)
            end
        end
    end)
end

setupFlingMechanics() 

--I see you skidder
