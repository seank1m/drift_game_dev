using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CarController : MonoBehaviour
{
    public float MovingSpeed = 100; // Acceleration
    public float MaxSpeed = 15; // Max speed
    public float DragConstant = 0.99f; // Slows down car to reach 0 with each frame 
    public float SteeringAngle = 20;
    public float Traction = 1; 
    private Vector3 MovingForce; // Speed 

    void Start()
    {
        Mesh mesh = GetComponent<MeshFilter>().mesh;
        mesh.RecalculateBounds();
    }

    // Update is called once per frame
    void Update()
    {
        // ------------------------------------------------------------- Moving -------------------------------------------------------------------------- 

        // Increase the moving force in the forward direction, get up and down arrows as inputs, and get delta time to keep frame drops into account
        MovingForce += transform.forward * MovingSpeed * Input.GetAxis("Vertical") * Time.deltaTime; 
        
        transform.position += MovingForce * Time.deltaTime;

        MovingForce *= DragConstant;

        // Ensure the length of vector does not exceed max speed vector (speed cap)
        MovingForce = Vector3.ClampMagnitude(MovingForce, MaxSpeed);

        Debug.DrawRay(transform.position, MovingForce.normalized * 3);
        Debug.DrawRay(transform.position, transform.forward * 3, Color.blue);

        // ------------------------------------------------------------ Steering ------------------------------------------------------------------------- 

        // Control turning / steering with left and right. Values are between - 1 and 1 
        float steeringControl = Input.GetAxis("Horizontal");

        // Rotate the car on Z axis by the steering angle only when the car is moving 
        transform.Rotate(Vector3.up * steeringControl * MovingForce.magnitude * SteeringAngle * Time.deltaTime); 

        // ------------------------------------------------------------ Traction -------------------------------------------------------------------------

        MovingForce = Vector3.Lerp(MovingForce.normalized, transform.forward, Traction * Time.deltaTime) * MovingForce.magnitude;
           // Syntax: Vector3.Lerp(a, b, valueZeroToOne)
    }
}
