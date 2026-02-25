# custom-corexy-printer
Documentation of my build process for a custom core xy 3d printer. 


project: Custom CoreXY Printer
owner: James Case
location: Yakima, WA

build_volume:
  target: 350x350x~400mm
  rails:
    X: MGN15-400mm
    Y: MGN12-400mm

frame:
  extrusion:
    type: 2060 and 2080 aluminum extrusion
  status: assembled, square, stiff

motion_system:
  type: CoreXY
  belts:
    type: GT2
    width: 9mm
    configuration: stacked high/low

  idlers:
    bore: 5mm
    types:
      - smooth idler pulley (backside contact)
      - toothed idler pulley (tooth engagement)
    mounting:
      shaft_type: 5mm precision shaft or M5 shoulder bolt
      stack_configuration: high and low planes

  x_gantry:
    rail: MGN12-400mm
    mounting: below XY interface plates
    datum_reference: XY interface plates define belt plane

xy_interface:
  manufacturer: SendCutSend
  material: 6061-T6 aluminum
  thickness: various (0.187", 0.250", 0.375")
  function: mount X gantry and define belt elevation

z_system:
  type: quad independent lead screws
  leveling: Klipper quad gantry leveling
  bed_plate:
    material: MIC6 aluminum preferred
    thickness: 8mm target

electronics:
  mainboard: BTT Manta M5P
  cpu: CB1
  toolhead: CANBUS planned

  secondary_board:
    model: BTT Manta EZ3
    function: dedicated quad Z control

bed_heater:
  type: AC silicone heater
  voltage: 110VAC
  control: SSR with 24V trigger

design_priority:
  - stiffness
  - precise belt alignment
  - clean CoreXY belt geometry
  - reliable quad-Z leveling

current_status:
  - frame assembled
  - XY interface plates ordered
  - idlers ordered
  - shim washers ordered
  - next_step: establish X gantry height datum
