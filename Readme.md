VIN Decoder API
============

VIN Decoder is a simple tool for decoding vehicle identification numbers. It returns the make, model, and more of the vehicle.

![Build Status](https://img.shields.io/badge/build-passing-green)
![Code Climate](https://img.shields.io/badge/maintainability-B-purple)
![Prod Ready](https://img.shields.io/badge/production-ready-blue)

This is a .NET Wrapper for the [VIN Decoder API](https://apiverve.com/marketplace/api/vindecoder)

---

## Installation

Using the .NET CLI:
```
dotnet add package APIVerve.API.VINDecoder
```

Using the Package Manager:
```
nuget install APIVerve.API.VINDecoder
```

Using the Package Manager Console:
```
Install-Package APIVerve.API.VINDecoder
```

From within Visual Studio:

1. Open the Solution Explorer.
2. Right-click on a project within your solution.
3. Click on Manage NuGet Packages...
4. Click on the Browse tab and search for "APIVerve.API.VINDecoder".
5. Click on the APIVerve.API.VINDecoder package, select the appropriate version in the right-tab and click Install.


---

## Configuration

Before using the vindecoder API client, you have to setup your account and obtain your API Key.  
You can get it by signing up at [https://apiverve.com](https://apiverve.com)

---

## Usage

The VIN Decoder API documentation is found here: [https://docs.apiverve.com/api/vindecoder](https://docs.apiverve.com/api/vindecoder).  
You can find parameters, example responses, and status codes documented here.

### Setup

###### Authentication
VIN Decoder API uses API Key-based authentication. When you create an instance of the API client, you can pass your API Key as a parameter.

```
// Create an instance of the API client
var apiClient = new VINDecoderAPIClient("[YOUR_API_KEY]", true);
```

---


### Perform Request
Using the API client, you can perform requests to the API.

###### Define Query

```
var queryOptions = new vindecoderQueryOptions {
  vin = "1HGCM82633A004352"
};
```

###### Simple Request

```
var response = apiClient.Execute(queryOptions);
if(response.error != null) {
	Console.WriteLine(response.error);
} else {
    var jsonResponse = JsonConvert.SerializeObject(response.data, Newtonsoft.Json.Formatting.Indented);
    Console.WriteLine(jsonResponse);
}
```

###### Example Response

```
{
  "status": "ok",
  "error": null,
  "data": {
    "ABS": "",
    "ActiveSafetySysNote": "",
    "AdaptiveCruiseControl": "",
    "AdaptiveDrivingBeam": "",
    "AdaptiveHeadlights": "",
    "AdditionalErrorText": "",
    "AirBagLocCurtain": "1st and 2nd Rows",
    "AirBagLocFront": "1st Row (Driver and Passenger)",
    "AirBagLocKnee": "",
    "AirBagLocSeatCushion": "",
    "AirBagLocSide": "1st Row (Driver and Passenger)",
    "AutoReverseSystem": "",
    "AutomaticPedestrianAlertingSound": "",
    "AxleConfiguration": "",
    "Axles": "",
    "BasePrice": "",
    "BatteryA": "",
    "BatteryA_to": "",
    "BatteryCells": "",
    "BatteryInfo": "",
    "BatteryKWh": "",
    "BatteryKWh_to": "",
    "BatteryModules": "",
    "BatteryPacks": "",
    "BatteryType": "",
    "BatteryV": "",
    "BatteryV_to": "",
    "BedLengthIN": "",
    "BedType": "Not Applicable",
    "BlindSpotIntervention": "",
    "BlindSpotMon": "",
    "BodyCabType": "Not Applicable",
    "BodyClass": "Coupe",
    "BrakeSystemDesc": "",
    "BrakeSystemType": "",
    "BusFloorConfigType": "Not Applicable",
    "BusLength": "",
    "BusType": "Not Applicable",
    "CAN_AACN": "",
    "CIB": "",
    "CashForClunkers": "",
    "ChargerLevel": "",
    "ChargerPowerKW": "",
    "CoolingType": "",
    "CurbWeightLB": "",
    "CustomMotorcycleType": "Not Applicable",
    "DaytimeRunningLight": "",
    "DestinationMarket": "",
    "DisplacementCC": "2998.832712",
    "DisplacementCI": "183",
    "DisplacementL": "2.998832712",
    "Doors": "2",
    "DriveType": "",
    "DriverAssist": "",
    "DynamicBrakeSupport": "",
    "EDR": "",
    "ESC": "",
    "EVDriveUnit": "",
    "ElectrificationLevel": "",
    "EngineConfiguration": "V-Shaped",
    "EngineCycles": "",
    "EngineCylinders": "6",
    "EngineHP": "240",
    "EngineHP_to": "",
    "EngineKW": "",
    "EngineManufacturer": "",
    "EngineModel": "J30A4",
    "EntertainmentSystem": "",
    "ErrorCode": "0",
    "ErrorText": "0 - VIN decoded clean. Check Digit (9th position) is correct",
    "ForwardCollisionWarning": "",
    "FuelInjectionType": "",
    "FuelTypePrimary": "Gasoline",
    "FuelTypeSecondary": "",
    "GCWR": "",
    "GCWR_to": "",
    "GVWR": "Class 1C: 4,001 - 5,000 lb (1,814 - 2,268 kg)",
    "GVWR_to": "Class 1: 6,000 lb or less (2,722 kg or less)",
    "KeylessIgnition": "",
    "LaneCenteringAssistance": "",
    "LaneDepartureWarning": "",
    "LaneKeepSystem": "",
    "LowerBeamHeadlampLightSource": "",
    "Make": "HONDA",
    "MakeID": "474",
    "Manufacturer": "AMERICAN HONDA MOTOR CO., INC.",
    "ManufacturerId": "988",
    "Model": "Accord",
    "ModelID": "1861",
    "ModelYear": "2003",
    "MotorcycleChassisType": "Not Applicable",
    "MotorcycleSuspensionType": "Not Applicable",
    "NCSABodyType": "",
    "NCSAMake": "",
    "NCSAMapExcApprovedBy": "",
    "NCSAMapExcApprovedOn": "",
    "NCSAMappingException": "",
    "NCSAModel": "",
    "NCSANote": "",
    "NonLandUse": "",
    "Note": "",
    "OtherBusInfo": "",
    "OtherEngineInfo": "",
    "OtherMotorcycleInfo": "",
    "OtherRestraintSystemInfo": "Seat Belt (Rr center position)",
    "OtherTrailerInfo": "",
    "ParkAssist": "",
    "PedestrianAutomaticEmergencyBraking": "",
    "PlantCity": "MARYSVILLE",
    "PlantCompanyName": "",
    "PlantCountry": "UNITED STATES (USA)",
    "PlantState": "OHIO",
    "PossibleValues": "",
    "Pretensioner": "",
    "RearAutomaticEmergencyBraking": "",
    "RearCrossTrafficAlert": "",
    "RearVisibilitySystem": "",
    "SAEAutomationLevel": "",
    "SAEAutomationLevel_to": "",
    "SeatBeltsAll": "Manual",
    "SeatRows": "",
    "Seats": "",
    "SemiautomaticHeadlampBeamSwitching": "",
    "Series": "",
    "Series2": "",
    "SteeringLocation": "",
    "SuggestedVIN": "",
    "TPMS": "",
    "TopSpeedMPH": "",
    "TrackWidth": "",
    "TractionControl": "",
    "TrailerBodyType": "Not Applicable",
    "TrailerLength": "",
    "TrailerType": "Not Applicable",
    "TransmissionSpeeds": "5",
    "TransmissionStyle": "Automatic",
    "Trim": "EX-V6",
    "Trim2": "",
    "Turbo": "",
    "VIN": "1HGCM82633A004352",
    "ValveTrainDesign": "Single Overhead Cam (SOHC)",
    "VehicleDescriptor": "1HGCM826*3A",
    "VehicleType": "PASSENGER CAR",
    "WheelBaseLong": "",
    "WheelBaseShort": "",
    "WheelBaseType": "",
    "WheelSizeFront": "",
    "WheelSizeRear": "",
    "Wheels": "",
    "Windows": ""
  }
}
```

---

## Customer Support

Need any assistance? [Get in touch with Customer Support](https://apiverve.com/contact).

---

## Updates
Stay up to date by following [@apiverveHQ](https://twitter.com/apiverveHQ) on Twitter.

---

## Legal

All usage of the mailboxlayer website, API, and services is subject to the [APIVerve Terms of Service](https://apiverve.com/terms) and all legal documents and agreements.

---

## License
Licensed under the The MIT License (MIT)

Copyright (&copy;) 2024 APIVerve, and Evlar LLC

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.