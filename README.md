# Apple Device Size 
What is Apple Device Size about it? Sure, It talking about How to built constraint for all iPhone and iPad Size.

# Notes
Here is Device Size Information 

```
--------------------------------------------------- iPhone ---------------------------------------------------
4 / 4s                                                        = W: 320-pt H: 480-pt      Result Size: 800
5 / 5s / 5c / SE                                              = W: 320-pt H: 568-pt      Result Size: 888
6 / 6s / 7 / 8                                                = W: 375-pt H: 667-pt      Result Size: 1042
6+ / 6s+ / 7+ / 8+                                            = W: 414-pt H: 736-pt      Result Size: 1150
11 Pro / X / Xs                                               = W: 375-pt H: 812-pt      Result Size: 1187
11 / Xr                                                       = W: 414-pt H: 896-pt      Result Size: 1310
11 Pro Max / Xs Max                                           = W: 414-pt H: 896-pt      Result Size: 1310
12 / 13 Pro  /  12 / 13                                       = W: 390-pt H: 844-pt      Result Size: 1310
12 / 13 Pro Max                                               = W: 428-pt H: 926-pt      Result Size: 1310
---------------------------------------------------- iPad ----------------------------------------------------
5th Gen, 6th Gen, Air 2, Pro (9.2-in), Mini 5th Gen, Mini 4   = W: 768-pt H: 1024-pt     Result Size: 1792
7th Gen                                                       = W: 810-pt H: 1080-pt     Result Size: 1890
Air 3rd Gen, Pro (10.5-in)                                    = W: 834-pt H: 1112-pt     Result Size: 1946
Pro 1st, 2nd Gen (11-in)                                      = W: 834-pt H: 1194-pt     Result Size: 2028
Pro 1st, 2nd, 3rd, 4th Gen (12.9-in)                          = W: 1024-pt H: 1366-pt    Result Size: 2390
```

# Tutorials
How and What do I start with it? Sure! Start with first step.

1. the new files Notes: New File > Swift File. 
2. Copy this code to your folders.

```

enum ScreenType: String {
        case iPhones_4_4S = "iPhone 4 or iPhone 4S"
        case iPhonesSE = "iPhone SE"
        case iPhones6S_8 = "iPhone 6S, iPhone 7 or iPhone 8"
        case iPhones_6Plus_6sPlus_7Plus_8Plus = "iPhone 6 Plus, iPhone 6S Plus, iPhone 7 Plus or iPhone 8 Plus"
        case iPhones_X_11Pro = "iPhone X - iPhone 11 and iPhone 12 Mini"
        case iPhone_XR_11 = "iPhone XR or iPhone 11"
        case iPhoneXS_11ProMax = "iPhone XS to 11 ProMax"
        case iPhone12_12Pro = "iPhone 12 and iPhone 12 Pro"
        case iPhone12ProMax = "iPhone 12 Pro Max"
    
        case unknown
    }

    var screenType: ScreenType {
        switch UIScreen.main.nativeBounds.height {
        case 1136:
            return .iPhonesSE
        case 1334:
            return .iPhones6S_8
        case 1792:
            return .iPhone_XR_11
        case 1920, 2208:
            return .iPhones_6Plus_6sPlus_7Plus_8Plus
        case 2436:
            return .iPhones_X_11Pro // iPhone 12 mini (Updated: Confirmed worked on 13 Mini)
        case 2688:
            return .iPhoneXS_11ProMax
        case 2532:
            return .iPhone12_12Pro // iphone 12 and 12 pro (Updated: Confirmed worked on 13 and 13 Pro)
        case 2778:
            return .iPhone12ProMax // 12 pro max. (Updated: Confirmed worked on 13 Pro Max)
        default:
            return .unknown
        }
    }
    
```

3. Done, it was officially created it, but one more things to need be finish to built in your own design view controller to 
see if UILabel() has created from ViewText into screenType's statements to use constraint to make sure stay prefect Constraint in the All Apple Device's size!

Now make sure add import UIKit at tops 

```
import UIKit
```

# Built Constraint 
Now you enjoy to edit the constraint to test on your device or iOS Simulator to see if it was prefect.

# If Methods 

```
    func DisplayView(UIView: UIView) {
    
      let ViewText = UILabel()
      // You DON'T need to created this code in each device size statement! Save your storage! 
            
      if screenType == .iPhones6S_8 {
        
        // Built Constraint Code in here
           // bottomAnchor
           // leadingAnchor
           // trailingAnchor
           // heightAnchor
           
           ViewText.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor, constant: 168).isActive = true
           
           ViewText.bottomAnchor.constraint(equalTo: view.bottomAnchor).isActive = true
           
           ViewText.leadingAnchor.constraint(equalTo: view.safeAreaLayoutGuide.leadingAnchor, constant: -20).isActive = true
           
           ViewText.trailingAnchor.constraint(equalTo: view.safeAreaLayoutGuide.trailingAnchor).isActive = true
       
        
      } else if screenType == .iPhone12ProMax { 
      
      // Built Constraint Code in here
           // bottomAnchor
           // leadingAnchor
           // trailingAnchor
           // heightAnchor
           
           ViewText.topAnchor.constraint(equalTo: view.topAnchor, constant: 90).isActive = true
           
           ViewText.bottomAnchor.constraint(equalTo: topBackground.bottomAnchor, constant: -20).isActive = true
           
           ViewText.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 25).isActive = true
           
           ViewText.widthAnchor.constraint(equalTo: view.widthAnchor, multiplier: 0.5).isActive = true
           
      } else {
      
          Break 
          
      }
      
      view.addSubview(ViewText)
    
   }
   
```

# Switch Methods

```
   func DisplayView(UIView: UIView) {
    
      let ViewText = UILabel()
      // You DON'T need to created this code in each device size statement! Save your storage! 
            
      switch screenType {
   
        case .iPhones6S_8:
         // Built Constraint Code in here
            // bottomAnchor
            // leadingAnchor
            // trailingAnchor
            // heightAnchor
           
            ViewText.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor, constant: 168).isActive = true
           
            ViewText.bottomAnchor.constraint(equalTo: view.bottomAnchor).isActive = true
           
            ViewText.leadingAnchor.constraint(equalTo: view.safeAreaLayoutGuide.leadingAnchor, constant: -20).isActive = true
           
            ViewText.trailingAnchor.constraint(equalTo: view.safeAreaLayoutGuide.trailingAnchor).isActive = true
        
        case .iPhone12ProMax:
    
         // Built Constraint Code in here
            // bottomAnchor
            // leadingAnchor
            // trailingAnchor
            // heightAnchor
           
            ViewText.topAnchor.constraint(equalTo: view.topAnchor, constant: 90).isActive = true
           
            ViewText.bottomAnchor.constraint(equalTo: topBackground.bottomAnchor, constant: -20).isActive = true
           
            ViewText.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 25).isActive = true
           
            ViewText.widthAnchor.constraint(equalTo: view.widthAnchor, multiplier: 0.5).isActive = true
        
        case .unknown:
        
            break
            
      }
      view.addSubview(ViewText)
    
   }
```

Notes: You can add more if statements or Switch statements to choose any types of device like here below lists 

```
.iPhones6S_8 
.iPhone_XR_11
.iPhones_6Plus_6sPlus_7Plus_8Plus
.iPhones_X_11Pro
.iPhoneXS_11ProMax
.iPhone12_12Pro 
.iPhone12ProMax
```

# Final
Fianlly, Now you need to this code to read to call the function called DisplayView() into this code from any View Controller what you want to display it. 

```
 override func viewDidLoad() {
       super.viewDidLoad()
       
       DisplayView()
       
  }
```

# BINGO! Here is your first prefect constraint in all devices at once you built code in all Screen Type! ENJOY!

       
