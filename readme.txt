SceneChange.cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEditor.SceneManagement;
public class SceneChange : MonoBehaviour
{
 
 public string sceneName;
 void OnTriggerEnter( )
 {
 
 EditorSceneManager.LoadScene(sceneName);
 }
}
Trampoline.cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
public class Trampoline : MonoBehaviour
{
 void OnTriggerEnter(Collider other)
 {

 other.GetComponent<Jump>().jumpStrength = 10;
 }
 void OnTriggerExit(Collider other)
 {
 //Уменьшение силы прыжка
 other.GetComponent<Jump>().jumpStrength = 2;
 }
}
Teleport.cs
using System.Collections;
 М1У1. Знакомство с Unity
87
using System.Collections.Generic;
using UnityEngine;
public class Teleport : MonoBehaviour
{
 public Transform teleportPoint;
 void OnTriggerEnter(Collider other)
 {

 other.transform.position = teleportPoint.position;
 }
}