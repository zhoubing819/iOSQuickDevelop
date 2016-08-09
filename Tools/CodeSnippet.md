# 常用代码片段

## Common

### .gitignore

~~~shell
# Created by https://www.gitignore.io

# Xcode
build/
*.pbxuser
!default.pbxuser
*.mode1v3
!default.mode1v3
*.mode2v3
!default.mode2v3
*.perspectivev3
!default.perspectivev3
xcuserdata
*.xccheckout
*.moved-aside
DerivedData
*.xcuserstate
*.hmap
*.ipa

# AppCode
.idea

# CocoaPods
#
# We recommend against adding the Pods directory to your .gitignore. However
# you should judge for yourself, the pros and cons are mentioned at:
# http://guides.cocoapods.org/using/using-cocoapods.html#should-i-ignore-the-pods-directory-in-source-control
#
# Pods/

# Carthage
#
# Add this line if you want to avoid checking in source code from Carthage dependencies.
# Carthage/Checkouts

Carthage/Build

# OSX
.DS_Store
.AppleDouble
.LSOverride

# Icon must end with two \r
Icon

# Thumbnails
._*

# Files that might appear in the root of a volume
.DocumentRevisions-V100
.fseventsd
.Spotlight-V100
.TemporaryItems
.Trashes
.VolumeIcon.icns

# Directories potentially created on remote AFP share
.AppleDB
.AppleDesktop
Network Trash Folder
Temporary Items
.apdisk
images/logo.sketch

# fastlane specific
fastlane/report.xml

# deliver temporary files
fastlane/Preview.html

# snapshot generated screenshots
fastlane/screenshots/**/*.png
fastlane/screenshots/screenshots.html

# scan temporary files
fastlane/test_output
test_output
fastlane/.env
pre-change.yml
.build
fastlane/README.md

~~~

## Objective-C

## Swift

### 单例

~~~swift
class MyManager  {
    static let sharedInstance = MyManager()
    private init() {}
}
~~~

### Mark

~~~swift
// MARK: - <#mark#>
~~~

### Log

~~~swift
func printLog<T>(message: T,
                    file: String = #file,
                  method: String = #function,
                    line: Int = #line)
{
    #if DEBUG
    print("\((file as NSString).lastPathComponent)[\(line)], \(method): \(message)")
    #endif
}
~~~

### dispatch_after

~~~swift
let delayTime = dispatch_time(DISPATCH_TIME_NOW, Int64(<#seconds#> * Double(NSEC_PER_SEC)))
dispatch_after(delayTime, dispatch_get_main_queue()) {
	<#statement#>
}
~~~