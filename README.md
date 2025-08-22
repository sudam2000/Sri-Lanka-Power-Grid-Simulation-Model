# Sri Lanka Power Grid Simulation Model 

An agent-based model simulating Sri Lanka's electrical power grid system with integrated renewable energy sources and battery energy storage systems (BESS).

## Overview

This NetLogo model provides a comprehensive simulation of Sri Lanka's power generation, transmission, and consumption network. The model focuses on the challenges and opportunities of integrating renewable energy sources (solar, wind, hydro) with battery storage systems while maintaining grid stability and economic viability.

## Key Features

- **Real-world Geographic Integration**: Uses actual Sri Lankan GIS data for provinces and districts
- **Comprehensive Energy Sources**: Solar, wind, hydro, thermal (coal/diesel), and biomass power plants
- **Advanced Battery Management**: Smart charging/discharging algorithms with efficiency modeling
- **Dynamic Weather System**: Realistic weather patterns affecting renewable generation
- **Economic Modeling**: Market dynamics, fuel prices, carbon taxation, and renewable subsidies
- **Multi-agent System**: Suppliers, distributors, and consumers with realistic behaviors
- **Grid Stability Analysis**: Real-time calculation of supply-demand balance and system reliability

## System Requirements

- NetLogo 6.0 or later
- Required extensions: `gis`, `table`, `csv`
- GIS data files (included in `data/` directory):
  - `lka_admbnda_adm0_slsd_20220816.shp` (country boundary)
  - `lka_admbnda_adm1_slsd_20220816.shp` (provinces)
  - `lka_admbnda_adm2_slsd_20220816.shp` (districts)

## Installation

1. Ensure NetLogo 6.0+ is installed
2. Clone or download this repository
3. Place the model file (`sri_lanka_energy_model_V6.nlogo`) and `data/` folder in the same directory
4. Open the `.nlogo` file in NetLogo

## Model Components

### Agents

**Suppliers (24 agents)**
- Major power plants positioned based on actual locations
- Includes renewable facilities with battery storage systems
- Examples: Hambantota Solar Farm, Mannar Wind Farm, Victoria Hydro Plant

**Distributors (4 agents)**
- Ceylon Electricity Board (CEB) regional divisions
- Transmission capacity and grid loss modeling

**Consumers (Population-based)**
- Distributed across districts based on actual demographic data
- Three types: residential, industrial, commercial
- Demand elasticity and satisfaction modeling

### Energy Sources Modeled

| Type | Facilities | Total Capacity | Battery Integration |
|------|------------|----------------|-------------------|
| Solar | 8 farms | 2,980 MW | Yes (1,490 MWh) |
| Wind | 7 farms | 1,350 MW | Yes (675 MWh) |
| Hydro | 3 complexes | 2,300 MW | No |
| Thermal | 3 plants | 1,700 MW | No |
| Biomass | 1 plant | 150 MW | No |

## Usage

### Basic Operation

1. **Setup**: Click "Setup" to initialize all agents and load GIS data
2. **Run**: Click "Go" to start continuous simulation or "Step" for single-step execution
3. **Monitor**: Observe real-time plots and system metrics

### Controls

#### Weather Parameters
- `solar-irradiance` (0-1): Solar generation potential
- `wind-speed` (0-1): Wind generation potential  
- `rainfall-level` (0-1): Hydro generation capacity
- `weather-volatility` (0-1): Weather change randomness
- `temperature` (20-40°C): Ambient temperature

#### Market Parameters
- `fuel-price-index` (0.5-3): Thermal generation cost multiplier
- `carbon-tax-rate` (0-20,000 Rs/ton): Environmental cost for thermal plants
- `renewable-subsidy` (0-5,000 Rs/MWh): Government incentive for renewables

#### System Controls
- `auto-weather?`: Enable automatic weather pattern changes
- `pause-simulation?`: Stop/resume simulation
- `show-consumer-satisfaction`: Display consumer metrics

### Emergency Scenarios

The model includes several emergency scenario buttons:
- `emergency-demand-increase`: Increase system demand by 20%
- `emergency-demand-decrease`: Decrease system demand by 20%
- Weather presets: `set-sunny-weather`, `set-windy-weather`, `set-rainy-weather`, `set-cloudy-weather`

## Key Metrics Monitored

- **System Generation**: Total MW output by source type
- **Renewable Percentage**: Share of clean energy in generation mix
- **Grid Stability**: System reliability index (0-1)
- **Battery Utilization**: Storage system usage percentage
- **Average Price**: System-wide electricity pricing (Rs/MWh)
- **Supply-Demand Balance**: Generation adequacy ratio
- **Blackout Risk**: Regional power shortage probability

## Battery Management System

The model features an advanced battery management system:

### Charging Logic
- Batteries charge during excess renewable generation
- Charging rate limited by technical specifications
- Storage efficiency losses modeled (87-92%)

### Discharging Logic
- Automatic discharge during supply deficits
- Grid support during peak demand periods
- Discharge efficiency and cycle counting

### Visual Indicators
- **Green**: Battery charging
- **Orange**: Battery discharging  
- **Red**: Low battery state (<20%)
- **Lime**: Full battery state (>80%)

## Research Applications

This model is suitable for analyzing:

- **Renewable Energy Integration**: Impact of increasing renewable share on grid stability
- **Battery Storage Optimization**: Sizing and operation strategies for BESS
- **Policy Analysis**: Effects of subsidies, carbon pricing, and regulations
- **Climate Resilience**: Grid response to extreme weather events
- **Economic Planning**: Cost-benefit analysis of different energy scenarios

## Model Validation

The model incorporates real-world data:
- Actual power plant locations and capacities
- Historical weather patterns for Sri Lanka
- Current electricity tariff structures
- Population distribution by district
- Regional demand characteristics

## BehaviorSpace Experiments

Included experiment: `renewable_stability_analysis`
- Tests renewable integration under varying weather volatility
- Analyzes impact of different subsidy levels
- 20 repetitions over 720 time steps (30 days)

## Limitations

- Simplified transmission network modeling
- Aggregated consumer behavior representation
- Static power plant characteristics
- Limited demand response capabilities
- Weather patterns based on statistical models rather than meteorological forecasting

## Data Sources

- Ceylon Electricity Board (CEB) statistical yearbooks
- Sri Lanka Sustainable Energy Authority reports
- Department of Census and Statistics population data
- Administrative boundary data from Survey Department of Sri Lanka
- Global fuel price indices and renewable energy cost databases

