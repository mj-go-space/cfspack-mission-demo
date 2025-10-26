# CFSPack Mission Demo

##  개요
이 리포지토리는 `CCSDS Codec` 과 `FDIR FSM` 모듈을 통합하여
소형 위성 미션을 시뮬레이션하는 구조를 보여줍니다.
NASA, ESA, KARI의 소프트웨어 표준 구조를 참고해 설계되었으며,
Mission Control 수준의 Fault-Response Flow 를 포함함.
---

## � Repository Structure

docs/mission_spec.md # Mission design specification
docs/assurance_case.md # Reliability and assurance documentation
ci/github-actions.yml # CI pipeline for documentation validation



---

## Mission Architecture
| Subsystem | Function |
|------------|-----------|
| **EPS (Electrical Power System)** | Monitors voltage/current and detects low-power conditions |
| **COMMS (Communication)** | Handles CCSDS-based telemetry/telecommand packets |
| **OBC (Onboard Computer)** | Executes FDIR FSM and manages recovery loops |

---

## Simulation Objectives
- Enter **SAFE Mode** upon low-voltage detection  
- Switch to **DEGRADED Mode** under over-temperature condition  
- Retry transmission up to **3 times** on packet loss before returning to **NOMINAL Mode**

---

## Future Development
- Integrate with **OpenMCT Dashboard** for real-time telemetry visualization  
- Connect with **Basilisk** or **Trick** simulators for dynamic mission testing  
- Apply **NASA GSFC CCSDS** data format and validation standards  
- Extend with encryption and onboard software update modules  

---

## Build & Validation
```bash
# Clone the repository
git clone git@github.com:mj-go-space/cfspack-mission-demo.git
cd cfspack-mission-demo

# Validate documentation structure
cat docs/mission_spec.md
cat docs/assurance_case.md
