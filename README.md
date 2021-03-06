# TextView

> The missing TextView in SwiftUI

## Download

- File -> Swift Packages -> Add Package Dependency...
- Select your project
- Enter `https://github.com/kenmueller/TextView` for the package repository URL
- Select **Branch**: master
- Click **Finish**

## Inputs

- `text: Binding<String>`
- `isEditing: Binding<Bool>`
	- The `TextView` will modify the value when it is selected and deselected
	- You can also modify this value to automatically select and deselect the `TextView`
- `placeholder: String? = nil`
- `textAlignment: TextView.TextAlignment = .left`
- `placeholderAlignment: Alignment = .topLeading`
- `placeholderHorizontalPadding: CGFloat = 4.5`
- `placeholderVerticalPadding: CGFloat = 7`
- `font: UIFont = .preferredFont(forTextStyle: .body)`
	- By default, the font is a body-style font
- `textColor: UIColor = .black`
- `placeholderColor: Color = .gray`
- `backgroundColor: UIColor = .white`
- `contentType: TextView.ContentType? = nil`
	- For semantic purposes only
- `autocorrection: TextView.Autocorrection = .default`
- `autocapitalization: TextView.Autocapitalization = .sentences`
- `isSecure: Bool = false`
- `isEditable: Bool = true`
- `isSelectable: Bool = true`
- `isScrollingEnabled: Bool = true`
- `isUserInteractionEnabled: Bool = true`

## Example

```swift
import SwiftUI
import TextView

struct ContentView: View {
    @State var input = ""
    @State var isEditing = false
    
    var body: some View {
        VStack {
            Button(action: {
                self.isEditing.toggle()
            }) {
                Text("\(isEditing ? "Stop" : "Start") editing")
            }
            TextView(
                text: $input,
                isEditing: $isEditing,
                placeholder: "Enter text here"
            )
        }
    }
}
```
