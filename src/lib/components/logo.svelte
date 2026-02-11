<svg
    width="200"
    height="150"
    viewBox="0 0 200 150"
    xmlns="http://www.w3.org/2000/svg"
    fill="none"
>
    <g id="sun" stroke="orange" stroke-width="3" stroke-linecap="round">
        <path d="M40 50 L20 30" />
        <path d="M50 40 L40 15" />
        <path d="M65 35 L65 10" />
        <path d="M80 40 L90 15" />
        <path d="M90 50 L110 30" />
        <path
            d="M45 60 Q 65 40 95 60"
            stroke-width="0"
            fill="orange"
            opacity="0.8"
        />
    </g>

    <g id="globe" stroke="#0056b3" stroke-width="3">
        <circle cx="100" cy="100" r="40" />
        <path d="M60 100 Q 100 120 140 100" fill="none" />
        <path d="M60 100 Q 100 80 140 100" fill="none" />
        <path d="M70 70 Q 100 90 130 70" fill="none" />
        <path d="M100 60 Q 80 100 100 140" fill="none" />
        <path d="M100 60 Q 120 100 100 140" fill="none" />
    </g>

    <path
        id="bannerPath"
        d="M50 120 Q 100 150 150 110"
        stroke="#6c757d"
        stroke-width="25"
        stroke-linecap="round"
        fill="none"
        opacity="0.9"
    />
    <path
        d="M50 120 Q 100 150 150 110"
        stroke="white"
        stroke-width="21"
        stroke-linecap="round"
        fill="none"
    />

    <text
        font-family="Arial, sans-serif"
        font-weight="bold"
        font-size="18"
        fill="#0056b3"
        letter-spacing="2"
    >
        <textPath
            href="#bannerPath"
            startOffset="50%"
            text-anchor="middle"
            dominant-baseline="middle"
        >
            SWBMT
        </textPath>
    </text>
</svg>
