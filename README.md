repeat wait()
until game:IsLoaded()

wait(1)

function Get_Board()
   
        end
    end
end

function Dupe(board)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(board.Controls.Close.Pad.CFrame.X, board.Controls.Close.Pad.CFrame.Y + 5, board.Controls.Close.Pad.CFrame.Z)
   
end

function Drop(amt)
    for i=1, amt do
        game:GetService("ReplicatedStorage").RemoteEvents.Equip:FireServer(getgenv().item_name)
        wait(0.7)
        game:GetService("ReplicatedStorage").RemoteEvents.Drop:FireServer(getgenv().item_name)
        wait(0.7)
    end
end

local board = Get_Board()

local platform = Instance.new("Part")
platform.Parent = workspace
platform.Position = Vector3.new(board.MAIN.CFrame.X, board.MAIN.CFrame.Y + 10, board.MAIN.CFrame.Z + 10)
platform.Anchored = true

wait()

game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(board.Controls.Close.Pad.CFrame.X, board.Controls.Close.Pad.CFrame.Y + 5, board.Controls.Close.Pad.CFrame.Z)
Drop(50)
wait(1)
Dupe(board)
