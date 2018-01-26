# Open app in specific view when user taps on push notification with iOS Swift

## The file 'GoogleService-Info.plist' needs to be generated on Firebase site to compile this project.

## [AppDelegate.swift]

```swift
       
    func navigateToView() {
        
        let storyboard = UIStoryboard.init(name: "Main", bundle: nil)
        
        for child in (self.window?.rootViewController?.childViewControllers)! {
            
            if child.restorationIdentifier == "Three" {
                
                let tabbarcontroller = self.window?.rootViewController as! MainTabViewController
                
                // Select TabBarItem with Index = 2
                tabbarcontroller.selectedIndex = 2
                
                let listTableViewController = (child.childViewControllers[0]) as! ListTableViewController
                let booksTableViewController = (storyboard.instantiateViewController(withIdentifier: "Four")) as! BooksTableViewController
                
                listTableViewController.navigationController?.pushViewController(booksTableViewController, animated: true)
            }
        }
        
    }

```

## Main.Storyboard

![GitHub Logo](https://raw.githubusercontent.com/mariohercules/ios-notification/master/TestNotification/Resourses/Main_storyboard.png)

