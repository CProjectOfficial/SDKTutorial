```c++
#include "CProjectSDK.hpp"

void ImGuiInitialize()
{
  // Some code ...
  
  ImGui::CreateContext( );
  
  // CProject::Initialize( CProjectDxImage DxImage, CProjectDXDevice DxDevice, bool ShouldLoadImage, bool ShouldLoadFont )
  //
  // * If you don't want to load an image set DxImage and ShouldLoadImage to NULL ( 0 )
  // * DxDevice parameter is REQUIRED if you are loading an image.
  // * ShouldLoadFont should be set to TRUE. If not, you will be set with the default IMGUI font.
  
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
