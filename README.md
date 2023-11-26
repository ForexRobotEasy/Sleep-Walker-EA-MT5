# Sleep Walker EA MT5

This code is for the Sleep Walker EA MT5, developed by Forex Robot Easy Team. Please note that ForexRobotEasy is not the official developer of this product, but we are providing a sample code that can work as described in this product. For detailed reviews and trading results of this product, please visit [Forex Robot Easy](https://forexroboteasy.com/forex-robot-review/sleep-walker-ea-mt5-review-optimize-night-trades/).

## Description

The Sleep Walker EA MT5 is designed to trade during night time between 22:00 and 06:00. It calculates entry points for two currency pairs, GBPUSD and EURUSD, and places pending orders with stop loss and profit booking levels.

## How it Works

1. The EA checks if the current time is within the desired trading period (night time) by calling the `IsNightTime()` function.
2. If it is night time, the EA calculates the entry points for GBPUSD and EURUSD by calling the `CalculateEntry()` function.
3. The EA then places pending orders with the calculated entry points, stop loss level, and profit booking level by calling the `PlacePendingOrder()` function.

## Libraries Used

This code includes the following libraries:
- Trade.mqh
- PositionInfo.mqh

## Constants

The following constants are defined:
- `SYMBOL_GBPUSD` - Symbol for GBPUSD currency pair
- `SYMBOL_EURUSD` - Symbol for EURUSD currency pair
- `TIMEFRAME_M5` - Timeframe set to M5 (5 minutes)
- `MAX_SLIPPAGE` - Maximum allowed slippage in points

## Global Variables

The following global variables are defined:
- `trade` - CTrade object used for trading operations
- `positionInfo` - CPositionInfo object used for retrieving position information

## Initialization

The `OnInit()` function is called during EA initialization. In this function, the stop loss and profit booking levels for pending orders are set. The trade and position info objects are also initialized with expert magic numbers.

## Start

The `OnStart()` function is called when the EA starts trading. It first checks if it is night time by calling the `IsNightTime()` function. If it is night time, it calculates the entry points for GBPUSD and EURUSD by calling the `CalculateEntry()` function. Finally, it places pending orders with the calculated entry points, stop loss level, and profit booking level by calling the `PlacePendingOrder()` function.

## Night Time Check

The `IsNightTime()` function checks if the current time is between 22:00 and 06:00. It gets the current time in seconds, converts it to a struct, and checks the hour component of the struct to determine if it is night time.

## Calculate Entry Point

The `CalculateEntry()` function is where the custom entry calculation logic should be implemented. It returns the calculated entry point for a given symbol.

## Place Pending Order

The `PlacePendingOrder()` function calculates the slippage in points based on the maximum allowed slippage and then places the pending order using the `BuyStop()` function of the `trade` object.

## Deinitialization

The `OnDeinit()` function is called when the EA is being deinitialized. It cleans up any resources used by the EA by calling the `Deinit()` functions of the `trade` and `positionInfo` objects.

Please note that this is a sample code provided by ForexRobotEasy and the actual implementation and functionality may vary. To find the official developer of this product, please use MQL5.
