# PalletWarehouse
Virtual factory built in Factory I/O: boxes are stacked on pallets in alternating layers, then stored in two multi-level racks served by two stacker cranes. Written in SCL for a Siemens S7-1500, with a WinCC HMI for browsing the racks and retrieving pallets.

## Features
- Palletizer with a 13-step state machine: box feed, pusher, layer clamp, trapdoor plate, elevator and pallet feeder. Layers alternate orientation (2 boxes x 3 pushes, then 3 boxes x 2 pushes, rotated) and a pallet has 3 layers.
- Two racks, 54 slots each (6 columns x 9 levels). Slot number maps directly to the crane TargetPosition, so no coordinate conversion is needed.
- Slot database: status (free / reserved / occupied), pallet ID and storage timestamp, kept in DBs.
- Load and unload run in parallel. A crane is available to a job only if it is not busy and not claimed by the other manager.
- Rack selection for new pallets: skip racks with no free slots or with a busy crane, prefer the rack with more free slots, alternate on a tie.
- HMI: one screen per rack with a slot map, a pop-up with slot details, and a confirmed "Retrieve pallet" action. Also has a panel with information about crane status, occupied slots and Start/Stop buttons.
## Preview
### Main Scene
<img width="1676" height="785" alt="obraz" src="https://github.com/user-attachments/assets/86e6b7ad-2b60-46c9-b1e2-943c3a0e02d3" />

### HMI
<img width="445" height="332" alt="obraz" src="https://github.com/user-attachments/assets/53b64f4c-07c3-441f-a4f9-acf9f894c228" />
<img width="445" height="332" alt="obraz" src="https://github.com/user-attachments/assets/1b12910c-902e-40cd-aa1c-fd93a3e476b3" />

