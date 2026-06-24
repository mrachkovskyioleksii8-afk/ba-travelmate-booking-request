# Feature: Bonus Points for Successful Bookings

## Use Case: Awarding Bonus Points for Successful Bookings

This activity diagram describes the process of awarding bonus points after a successful booking payment. 
It includes the main flow, an unsuccessful payment scenario, 
and a scenario where the user closes the payment page before completing the payment.

```mermaid

flowchart TD
    Start(( )) --> Trigger[User clicks Confirm Booking]
    Trigger --> Redirect[System redirects user to payment page]
    Redirect --> UserPay{Payment?}

    UserPay -->|Yes| Pay[User completes payment]
    Pay --> PaySuccess{Success?}

    PaySuccess -->|Yes| RecordSuccess[System records successful payment]
    RecordSuccess --> BookingSuccess[Booking successful]
    BookingSuccess --> AwardBonus[System awards bonus points]
    AwardBonus --> UpdateBalance[System updates bonus account balance]
    UpdateBalance --> SendPush[System sends push notification]
    SendPush --> BonusAvailable[Bonus available in bonus account]
    BonusAvailable --> EndMain(((End)))

    PaySuccess -->|No| RecordFail[System records unsuccessful payment]
    RecordFail --> NoBonusA1[System does not award bonus]
    NoBonusA1 --> Wait[Waiting for payment retry 15 min]
    Wait --> Retry{Retry?}
    Retry -->|Yes| Pay
    Retry -->|No| Cancelled[Booking cancelled]
    Cancelled --> EndA1(((End)))

    UserPay -->|No| ClosePage[User closes payment page]
    ClosePage --> RecordAbsence[System records absence of payment]
    RecordAbsence --> NoBonusA2[System does not award bonus]
    NoBonusA2 --> EndA2(((End)))

    classDef init fill:#333,stroke:#333,color:#333
    classDef fin fill:#fff,stroke:#333,stroke-width:2px,font-size:7px

    class Start init
    class EndMain,EndA1,EndA2 fin

    style Start width:6px,height:6px,min-width:6px,min-height:6px
    style EndMain width:18px,height:18px,min-width:18px,min-height:18px,font-size:7px
    style EndA1 width:18px,height:18px,min-width:18px,min-height:18px,font-size:7px
    style EndA2 width:18px,height:18px,min-width:18px,min-height:18px,font-size:7px


```