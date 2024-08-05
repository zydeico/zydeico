```swift
//import Foundation
//
//let arrayOfByteArrays: [[UInt8]] = [
//    [77, 73, 73, 66, 73, 106, 65, 78, 66, 103, 107, 113, 104, 107, 105, 71, 57, 119, 48, 66, 65, 81, 69, 70, 65, 65, 79, 67, 65, 81, 56, 65, 77, 73, 73, 66, 67, 103, 75, 67, 65, 81, 69, 65, 115, 115, 76, 87, 115, 109, 114, 100, 48, 98, 120, 105, 66, 106, 102, 100, 55, 118, 116, 72, 32, 113, 83, 99, 114, 101, 113, 100, 57, 54, 86, 120, 73, 49, 101, 117, 101, 51, 122, 82, 51, 69, 85, 53, 52, 54, 118, 47, 102, 52, 66, 78, 69, 97, 72, 109, 53, 99, 99, 43, 90, 81, 51, 79, 74, 103, 75, 113, 110, 103, 74, 118, 86, 70, 103, 110, 103, 110, 100, 109, 101, 81, 69, 70, 67, 32, 47, 73, 97, 120, 49, 74, 66, 119, 43, 75, 97, 79, 120, 84, 52, 106, 82, 89, 104, 101, 113, 85, 87, 47, 43, 121, 68, 116, 47, 104, 68, 89, 80, 73, 86, 89, 49, 114, 106, 101, 112, 83, 51, 54, 105, 100, 121, 49, 83, 76, 86, 99, 51, 103, 108, 81, 97, 55, 75, 105, 80, 122, 114, 100, 32, 107, 118, 118, 97, 57, 113, 57, 50, 120, 67, 118, 122, 83, 86, 48, 100, 110, 79, 71, 78, 71, 52, 73, 82, 89, 88, 52, 117, 74, 89, 99, 82, 76, 110, 57, 101, 108, 75, 117, 43, 50, 72, 67, 79, 97, 115, 80, 80, 84, 86, 99, 104, 49, 106, 114, 87, 108, 47, 122, 107, 55, 79, 48, 82, 32, 121, 114, 76, 67, 50, 85, 89, 101, 72, 79, 102, 69, 72, 80, 101, 89, 65, 117, 81, 70, 122, 72, 122, 116, 53, 76, 89, 88, 121, 98, 109, 50, 107, 56, 102, 49, 48, 70, 112, 66, 107, 116, 82, 50, 47, 112, 85, 85, 112, 86, 56, 119, 76, 57, 55, 98, 78, 100, 66, 115, 104, 98, 111, 120, 32, 68, 98, 51, 70, 102, 118, 103, 108, 82, 111, 79, 56, 72, 67, 81, 49, 110, 88, 84, 52, 100, 67, 90, 86, 47, 65, 110, 107, 113, 103, 76, 53, 99, 68, 71, 72, 97, 111, 115, 75, 47, 122, 84, 54, 109, 71, 72, 81, 67, 82, 119, 56, 117, 69, 82, 102, 53, 52, 75, 101, 53, 120, 122, 89, 32, 55, 81, 73, 68, 65, 81, 65, 66]
//]
//
//for byteArray in arrayOfByteArrays {
//    let data = Data(byteArray)
//    if let urlString = String(data: data, encoding: .utf8) {
//        print("El arreglo de bytes decodeado es: \n\(urlString)")
//    } else {
//        print("No se pudo decodificar la cadena.")
//        
//    }
//}
//
//func byteArray(from base64String: String) -> [UInt8]? {
//    guard let data = Data(base64Encoded: base64String) else { return nil }
//    return [UInt8](data)
//}
//let base64String = "MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA8eUH7QH59B9XvJdWGypl/ZtuSYuGCBQqSfPDREFQb32s5N91a3W75SJNzEK7vAXlSZdD1eYXM7mNktME4beCOC1vmIbR6h30f82KtF5o5f0uz733kMrO+/YiMd+RjHv32DddMR7kkQ0x6+3z1A1ZezT+fLH4drPfrb/OKhS1gT2D3tVEs/boit3FoyljvAt/G0PwGOuuk0dr4dWn/SisAfeivlg0RLP+YWEku8yNmIzEidog00PISx5LbdIgdaHiKIHSvaL4dTXSc+wEF4BmF4wFfiAq87jdUJseJODDPY2UfbRMlQ3BsgzIfjpAwrv+er1fc3NSC3XeLa+1eAXayQIDAQAB"
//if let byteArray = byteArray(from: base64String) {
//    print("\nEl arreglo de bytes es: \n\(byteArray)")
//} else {
//    print("No se pudo decodificar la cadena base64.")
//}


import Foundation

enum Location: String {
    case Mexico
}

enum Languages: String {
    case Spanish
    case English
    
    var spanishName: String {
        switch self {
        case .Spanish:
            return "Español"
        case .English:
            return "Inglés"
        }
    }
}

extension Location {
    var description: String {
        return self.rawValue
    }
}

extension Languages {
    var description: String {
        return self.rawValue
    }
}

class Developer {
    
}

class Daniel: Developer {

    let name = "Daniel Vázquez"
    let age = 30
    let location: Location = .Mexico
    let languages: [Languages] = [.Spanish, .English]
    let programmingLanguages = ["Swift", "Objective-C", "JavaScript", "Python"]
    let markup = ["HTML", "CSS", ""]
    
    // New details
    let introduction = "Hello world!, I'm software engineer, which are your superpower?"
    let aboutMe = """
    About Me 🙌🏻

    * 📱  Apple platforms engineer
    * 💻  Frontend Developer
    * 👨🏻‍💻  Backend Developer
    * 🔓  Former security analyst
    * 🤖  AI researcher
    """
    let reachMe = "Reach me via 👇🏻\n[Linkedin](https://www.linkedin.com/in/jdanvz/)"

    func details() -> String {
        var details = ""
        
        for detail in Mirror(reflecting: self).children {
            guard let label = detail.label else { continue }
            
            if ["introduction", "aboutMe", "reachMe"].contains(label) {
                continue
            }
            
            if label == "languages" {
                if let languagesArray = detail.value as? [Languages] {
                    let languageNames = languagesArray.map { $0.spanishName }.joined(separator: ", ")
                    details.append("\(label.capitalized): \(languageNames)\n")
                }
            } else if let array = detail.value as? [CustomStringConvertible] {
                details.append("\(label.capitalized): [\(array.map { $0.description }.joined(separator: ", "))]\n")
            } else if let customDescription = detail.value as? CustomStringConvertible {
                details.append("\(label.capitalized): \(customDescription.description)\n")
            } else {
                details.append("\(label.capitalized): \(detail.value)\n")
            }
        }
        
        details.append("\n\(introduction)\n\n")
        details.append("\(aboutMe)\n\n")
        details.append("\(reachMe)\n")
        
        return details
    }
}

print(Daniel().details())

```
