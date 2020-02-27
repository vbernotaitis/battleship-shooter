# BattleShip Shooter

Interface that should be implemented:
```
public interface IBattleShipShooter
{
    /// <summary>
    /// Name of the captain
    /// </summary>
    string CaptainName { get; set; }

    /// <summary>
    /// Generates all ships with their coordinates.
    /// Fleet should consist of 10 ships: 1 of size 4, 2 of size 3, 3 of size 2, 4 of size 1.
    /// </summary>
    /// <returns>Fleet of ships</returns>
    Ship[] PrepareShipsForNewBattle();

    /// <summary>
    /// Shoots to the oponents fleet by the determined coordinates.
    /// </summary>
    /// <returns>Coordinates of the shot</returns>
    Coordinates Shoot();

    /// <summary>
    /// Reports result of the last shot.
    /// </summary>
    /// <param name="coordinates">Coordinates of the last shot</param>
    /// <param name="result">Shot result</param>
    void ReportLastShotResult(Coordinates coordinates, ShotResult result);

    /// <summary>
    /// Reports result of the last oponent's shot.
    /// </summary>
    /// <param name="coordinates">Coordinates of the oponent's last shot</param>
    /// <param name="result">Shot result</param>
    void ReportOponentsLastShotResult(Coordinates coordinates, ShotResult result);
}
```

Example:
```
public class BattleShipShooterExample : IBattleShipShooter
{
    public string CaptainName { get; set; } = "John";

    public Ship[] PrepareShipsForNewBattle()
    {
        return new[]
        {
            new Ship('A', 1, 'C', 1),
            new Ship('G', 2, 'H', 2),
            new Ship('J', 3, 'J', 3),
            new Ship('B', 4, 'D', 4),
            new Ship('F', 6, 'F', 6),
            new Ship('H', 6, 'I', 6),
            new Ship('D', 7, 'D', 10),
            new Ship('A', 8, 'A', 8),
            new Ship('F', 10, 'G', 10),
            new Ship('J', 9, 'J', 9)
        };
    }

    public Coordinates Shoot()
    {
        return new Coordinates('A', 1);
    }

    public void ReportLastShotResult(Coordinates coordinates, ShotResult result)
    {
    }

    public void ReportOponentsLastShotResult(Coordinates coordinates, ShotResult result)
    {
    }
}
```