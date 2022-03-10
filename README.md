# SwiftLintRules

[SwiftLint](https://github.com/realm/SwiftLint) is a library that we use in our projects to enforce Swift style and conventions.

The rules configuration for Swift lint can be found at /Fastlane/.swiftlint.yml.


## How to configure a new project to use SwiftLint?

Install the SwiftLint with Cocoapods
Add a new Run script:

Declare a variable depending in the project:
If the project is an APP:
```
FILE=${SRCROOT}/../Fastlane/.swiftlint.yml
```

If the project is a Module:
```
FILE=${SRCROOT}/../../Fastlane/.swiftlint.yml
```

Add following code to execute swift lint:

```
if [ -f $FILE ]; then
	"${PODS_ROOT}/SwiftLint/swiftlint" --config $FILE
fi
```

The `if` in the run script is to avoid a file not found error when a process is running in TeamCity.


## How to use swiftlint autoccorrect? 

Install swiftlint in your Mac:
```
brew install swiftlint
```

Use autocorrect in the Apps projects:
```
swiftlint autocorrect --config ../Fastlane/.swiftlint.yml
```

Use autocorrect in the Modules projects:
```
swiftlint autocorrect --config ../../Fastlane/.swiftlint.yml
```
