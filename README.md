```swift
import Foundation

enum Location: String {
    case mexico = "Mexico"
}

enum Language: String, CaseIterable {
    case spanish = "Spanish"
    case english = "English"
    
    var displayName: String { rawValue }
}

struct Daniel {
    let name = "Daniel Vázquez"
    let location: Location = .mexico
    let languages: [Language] = [.spanish, .english]
    let programmingLanguages = ["Swift", "Objective-C", "JavaScript", "Python", "TypeScript", "Kotlin", "Java", "Go"]
    let frameworks = ["NodeJS", "Django", "SwiftUI", "VueJS", "ReactJS", "NextJS", "JetPack Compose", "Vapor"]
    let cloudStack = ["AWS", "Google Cloud Platform", "Azure"]
    let databasesStack = ["NoSQL", "SQL", "PostgreSQL", "MongoDB"]
    let markup = ["HTML", "CSS"]
    let skills = ["Mobile developer", "Front-end developer", "Backend developer", "AI & ML researcher"]
    private let reachMe = "https://www.linkedin.com/in/jdanvz/"
    
    func composeGreeting() -> String {
        """
        Hi, I'm \(name), a developer from \(location.rawValue).
        I speak \(languages.map { $0.displayName }.joined(separator: ", ")).
        I work with programming languages like \(programmingLanguages.joined(separator: ", ")),
        and use frameworks such as \(frameworks.joined(separator: ", ")).
        I have experience with cloud technologies like \(cloudStack.joined(separator: ", ")),
        databases like \(databasesStack.joined(separator: ", ")),
        and markup languages like \(markup.joined(separator: ", ")).
        My main skills are \(skills.joined(separator: ", ")).
        Feel free to reach me on LinkedIn: \(reachMe)
        """
    }
}

print(Daniel().composeGreeting())
```
