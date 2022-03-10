# SwiftLintRules

[SwiftLint](https://github.com/realm/SwiftLint) is a library that we use in our projects to enforce Swift style and conventions.

The rules configuration for Swift lint can be found at /Fastlane/.swiftlint.yml.


## How to configure a new project to use SwiftLint?

Install the SwiftLint with Cocoapods
Add a new Run script:

```
FILE=.swiftlint.yml
curl -o $FILE https://raw.githubusercontent.com/robertrcosta/SwiftLintRules/main/.swiftlint.yml

if [ -f $FILE ]; then
"${PODS_ROOT}/SwiftLint/swiftlint" --config $FILE
fi
```

## How to use swiftlint autoccorrect? 

Install swiftlint in your Mac:
```
brew install swiftlint
```
