Date extension:

```swift
extension String {
    /// Convert date string to Date
    ///
    /// - Returns: a Date optional
    func dateString2Date() -> Date? {
        let dateFormatter = DateFormatter()
        dateFormatter.dateFormat = "yyyy-MM-dd"
        return dateFormatter.date(from: self)
    }
}

extension Date {
    /// get a normal description string
    ///
    /// - Returns: a description string
    func formatterString() -> String {
        let dateFormatter = DateFormatter()
            dateFormatter.dateFormat = "yyyy-MM-dd"
        return dateFormatter.string(from: self)
    }
    
    
    /// Get the day before today
    ///
    /// - Parameter number: the days number ago
    /// - Returns: ago date
    func GetNumberDaysBeforeToday(_ number: UInt,_ since: Date? = nil) -> Date {
        
        let agoDate: Date
        if let date = since {
           agoDate = Date(timeInterval: -24*60*60*(TimeInterval)(number), since: date)
        } else {
            agoDate = Date(timeInterval: -24*60*60*(TimeInterval)(number), since: self)
        }
        
        return agoDate
    }
    
    /// Get the day after today
    ///
    /// - Parameter number: the days number after
    /// - Returns: after date
    func GetNumberDaysAfterToday(_ number: UInt, _ since: Date? = nil) -> Date {
        
        let afterDate: Date
        if let date = since {
            afterDate = Date(timeInterval: 24*60*60*(TimeInterval)(number), since: date)
        } else {
            afterDate = Date(timeInterval: 24*60*60*(TimeInterval)(number), since: self)
        }
        return afterDate
    }
    
    /// 是否同一天
    func isSameDay(firstDate: Date,secondDate: Date) -> Bool {
        if firstDate.timeIntervalSince1970 == secondDate.timeIntervalSince1970 {
            return true
        } else {
            return false
        }
    }
}
```

