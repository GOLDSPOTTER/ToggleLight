using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ToggleLight : MonoBehaviour
{
    public GameObject lights;
    private new bool enabled;
    public void OnMouseDown()
    {
        enabled = !enabled;
        foreach (Transform light in lights.transform)
        {
            
            Transform pointLightTransform = light.Find("PointLight");

            if (pointLightTransform != null )
            {
                Light pointLight = pointLightTransform.GetComponent<Light>();
                if (pointLight)
                {
                    pointLight.enabled = enabled;
                }
            }
        }
    }
}
