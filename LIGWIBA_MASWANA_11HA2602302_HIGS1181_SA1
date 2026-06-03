using UnityEngine;

[RequireComponent(typeof(Rigidbody2D))]
public class EnemyAI : MonoBehaviour
{
    [Header("Movement Settings")]
    [Tooltip("Time (in seconds) it takes to move one tile.")]
    public float moveTime = 0.2f;

    private Rigidbody2D rb2D;
    private float inverseMoveTime;
    private Vector2 targetPosition;

    private void Awake()
    {
        // Cache the Rigidbody2D component
        rb2D = GetComponent();
    }

    private void Start()
    {
        // Calculate movement speed factor
        inverseMoveTime = 1f / moveTime;

        // Enemy starts at its current position
        targetPosition = rb2D.position;
    }

    /// <summary>
    /// Called by the GameManager when it's the enemy's turn.
    /// </summary>
    public void TakeTurn()
    {
        // --- CURRENT LOGIC: Moves randomly one tile ---
        Vector2[] directions = { Vector2.up, Vector2.down, Vector2.left, Vector2.right };
        Vector2 randomDir = directions[Random.Range(0, directions.Length)];
        targetPosition = rb2D.position + randomDir;

        // Instantly move enemy to the new position (grid-based movement)
        rb2D.MovePosition(targetPosition);

        Debug.Log("Enemy moved randomly.");
    }


