<script>
    let bridgeTraffic = [
{name: "Henry Hudson Bridge", traffic: 58809 },
{name: "Hugh L. Carey Tunnel", traffic: 54007},
{name: "Queens-Midtown Tunnel", traffic: 86081 },
{name: "R.F.K. Memorial Bridge Manhattan Plaza", traffic: 91509 },
{name: "George Washington Bridge", traffic: 280784 },
{name: "Holland Tunnel", traffic: 87232 },
{name: "Lincoln Tunnel", traffic: 109796 },
    ];

    bridgeTraffic.sort((a, b) => b.traffic - a.traffic);
</script>

<section>
    <h1>Bargraph of Bridge traffic</h1>
<svg>
{#each bridgeTraffic as bridge, i}
    <g transform={`translate(400 ${i * 20 + 200})`}>
        <rect width={bridge.traffic / 1000} height="10" fill="red" />
        <text font-size="12" text-anchor="end" dominant-baseline="middle" x="-5" y="5">{bridge.name}</text>
        <text fill="#aaa" font-size="12" dominant-baseline="middle" y="5" x="{bridge.traffic / 1000 + 10}">{bridge.traffic.toLocaleString()}</text>
    </g>
{/each}
</svg>
</section>


<style>
    p {
        color: black;
    }

    svg {
        border: 1px solid #ddd;
        width: 80%;
        height: 500px;
        margin: auto;
        
    }

    section {
        display: flex;
        align-items: center;
        flex-direction: column;
        justify-content: center;
        color: black;
        padding: 100px 0px;
        
    }
</style>