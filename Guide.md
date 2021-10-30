<h1> Overview </h1>
<h3> After purchasing your design and its completion, make sure you download the required SDK files and add them into your project accordingly.</h3>

```c++
#include "CProjectSDK.hpp"

void ImGuiInitialize()
{
  // Some code ...
  
  ImGui::CreateContext( );
  
  // CProject::Initialize( CProjectDxImage DxImage, CProjectDXDevice DxDevice, bool ShouldLoadImage, bool ShouldLoadFont )
  
  // @ Param: DxImage        | This should be left NULL if you're NOT loading an image.
  // @ Param: DxDevice       | This should be left NULL if you're NOT loading an image.
  // @ Param: ShoudLoadImage | This should be left NULL if you're NOT loading an image
  // @ Param: ShouldLoadFont | This should NOT be NULL. Unless you prefer the ImGui font.
  
  /*
     - Notes:
     
        If you're using DirectX 11, please goto "CProjectSDK.hpp" and 
        set "CPROJECT_USING_DX11" to "TRUE" an "CPROJECT_USING_DX9" to FALSE.    
  */
  
  CProject::SDK( )->Initialize( 0, 0, 0, true );
}

void DrawLoop() 
{
   // Some code ...
   
   static bool IsOpen = false;
   
   if ( GetAsyncKeyState(VK_INSERT) & true )
        IsOpen = !IsOpen;
        
   if ( IsOpen )
   {
      // Draw your beautiful design!
      CProject::SDK( )->Draw( );
   }
}
```
