# Class Diagram - Phần mềm quản lý chung cư BlueMoon

## 1. Các Class và Method

### Class User
#### Attributes:
- userId : int
- role : String
- apartmentId : int
- name : String
- birthday : Date
- gender : boolean
- phoneNumber : String
- nationality : String
- image : byte[]
- address : String
- isOwner : boolean
- relationshipWithOwner : String
- status : int

#### Methods:
- editInfo(): boolean

---

### Class Login
#### Attributes:
- userId : int
- username : String
- password : String

#### Methods:
- login(): boolean
- logout(): void
- changePassword(): boolean

---

### Class Resident (extends User)
#### Methods:
- addResident(): boolean
- deleteResident(): boolean
- updateResident(): boolean
- searchResidentByName(): List<Resident>

---

### Class Apartment
#### Attributes:
- apartmentId : int
- ownerId : int
- area : float
- floor : int
- room : String

#### Methods:
- addApartment(): boolean
- deleteApartment(): boolean
- updateOwner(): boolean
- searchApartmentByRoom(): Apartment
- statisticsResidents(): int

---

### Class Fee
#### Attributes:
- feeId : int
- name : String
- ratePerSquareMeter : double
- isMandatory : boolean
- feeType : String

#### Methods:
- addFee(): boolean
- deleteFee(): boolean
- updateFee(): boolean
- searchFeeByName(): List<Fee>

---

### Class Payment
#### Attributes:
- paymentId : int
- feeId : int
- apartmentId : int
- amountDue : double
- amountPaid : double
- paymentDate : Date
- payForMonth : int
- payForYear : int
- status : String

#### Methods:
- makePayment(): boolean
- createMonthlyPayment(): boolean
- viewPaidList(): List<Payment>
- viewUnpaidList(): List<Payment>
- viewOverdueList(): List<Payment>

---

### Class Vehicle
#### Attributes:
- vehicleId : int
- residentId : int
- type : String
- licensePlate : String

#### Methods:
- addVehicle(): boolean
- deleteVehicle(): boolean
- searchVehicleByLicensePlate(): Vehicle

---

### Class Activity
#### Attributes:
- activityId : int
- residentId : int
- status : int
- timeIn : Date
- timeOut : Date
- note : String

#### Methods:
- viewHistoryResidence(): List<Activity>



---


## 2. Kiểu Quan Hệ Giữa Các Class

| Loại Quan Hệ | Giữa Class | Multiplicity | Ý Nghĩa |
|--------------|------------|----------------|---------|
| Inheritance  | Resident → User | - | Kế thừa |
| Association  | Login → User | 1 ↔ 1 | Mỗi User bắt buộc có 1 Login duy nhất và ngược lại |
| Association  | Resident → Apartment | 0..* ↔ 1 | Nhiều Resident có thể ở cùng 1 Apartment |
| Composition  | Apartment (owner) → User (Owner) | 1 ↔ 1 | 1 Apartment bắt buộc có 1 Owner (User), xóa Apartment có thể xóa Owner |
| Association  | Activity → Resident | 0..* ↔ 1 | 1 Resident có thể có nhiều Activity |
| Association  | Vehicle → Resident | 0..* ↔ 1 | 1 Resident có thể có nhiều Vehicle |
| Aggregation  | Payment → Apartment | 0..* ↔ 1 | 1 Apartment có thể có nhiều Payment, nhưng Payment vẫn còn nếu Apartment bị xóa |
| Aggregation  | Payment → Fee | 0..* ↔ 1 | 1 Fee có thể áp dụng cho nhiều Payment, nhưng Payment vẫn còn nếu Fee bị xóa |

---

## Giải thích ký hiệu Multiplicity:

| Ký hiệu | Ý Nghĩa |
|---------|---------|
|1|Bắt buộc có 1|
|0..1|Có hoặc không|
|0..*|0 hoặc nhiều|
|1..*|1 hoặc nhiều|
|m..n|Tối thiểu m và tối đa n|

---

## Ghi chú:

- **Inheritance**: Kế thừa, class con được dùng lại thuộc tính và phương thức của class cha.
- **Association**: Liên kết, quan hệ ràng buộc giữa các class nhưng không chặt.
- **Composition**: Quan hệ chặt, xóa class chứa thì class thành phần bị xóa theo.
- **Aggregation**: Quan hệ rời rạc, xóa class chứa thì class thành phần vẫn còn.
- **Multiplicity**: Biểu diễn số lượng liên kết giữa các class.

