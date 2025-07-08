import React, { useState } from "react";
import Image from "next/image";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import { Star } from "lucide-react";

const tabs = [
  "Find Installer",
  "Report/Rate",
  "Awareness Hub",
  "Register Installer",
  "Blog & Updates",
  "Green Card",
];

export default function HomePage() {
  const [activeTab, setActiveTab] = useState("Find Installer");

  return (
    <div className="p-6 max-w-7xl mx-auto space-y-8 bg-yellow-100 min-h-screen">
      <header className="text-center space-y-4">
        <Image
          src="/fireflies-lightbulb.png"
          alt="FireFlies Energy Logo"
          width={120}
          height={120}
          className="mx-auto"
        />
        <h1 className="text-4xl font-bold text-black">FireFlies Solar Portal</h1>
        <p className="text-lg text-gray-700">
          Verified Solar Installers | Anti-Counterfeit Campaign | Safer Homes
        </p>
        <div className="mt-4 space-y-1">
          <p className="text-black font-semibold text-lg">“FireFlies Energy—Solar You Can Trust.”</p>
          <p className="text-black font-semibold text-lg">“Verified Installers. Safer Homes.”</p>
          <p className="text-black font-semibold text-lg">“No More Fires. No More Scams.”</p>
        </div>
      </header>

      {/* Custom Tab Component */}
      <nav className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-2 bg-yellow-300 p-2 rounded-xl text-center">
        {tabs.map((tab) => (
          <button
            key={tab}
            onClick={() => setActiveTab(tab)}
            className={`text-black font-medium py-1 px-2 rounded-md ${
              activeTab === tab ? "bg-white shadow" : ""
            }`}
          >
            {tab}
          </button>
        ))}
      </nav>

      {/* Tab Content (basic logic for demonstration) */}
      <div className="text-center text-sm text-gray-700">
        <p>Currently viewing: <strong>{activeTab}</strong></p>
      </div>

      {/* Installer Classification */}
      <section className="mt-6 space-y-6">
        <h2 className="text-2xl font-semibold text-black">Certified Installers by Region</h2>

        {/* Harare */}
        <div>
          <h3 className="text-xl font-bold text-black mb-2">Harare</h3>
          <Card className="bg-white border-yellow-500 border-2 shadow-md">
            <CardContent className="p-4 space-y-2">
              <h4 className="text-lg font-bold text-black">BrightSolar Energy</h4>
              <p className="text-gray-700">Certified by FireFlies | 7 Years Experience</p>
              <p className="flex items-center gap-1 text-yellow-500">
                <Star size={16} /> 4.8/5 (122 ratings)
              </p>
              <Button className="bg-yellow-400 text-black hover:bg-yellow-500">View Profile</Button>
            </CardContent>
          </Card>
        </div>

        {/* Bulawayo */}
        <div>
          <h3 className="text-xl font-bold text-black mb-2">Bulawayo</h3>
          <Card className="bg-white border-yellow-500 border-2 shadow-md">
            <CardContent className="p-4 space-y-2">
              <h4 className="text-lg font-bold text-black">SolarSecure Installations</h4>
              <p className="text-gray-700">Certified by FireFlies | 5 Years Experience</p>
              <p className="flex items-center gap-1 text-yellow-500">
                <Star size={16} /> 4.6/5 (89 ratings)
              </p>
              <Button className="bg-yellow-400 text-black hover:bg-yellow-500">View Profile</Button>
            </CardContent>
          </Card>
        </div>

        {/* Mutare */}
        <div>
          <h3 className="text-xl font-bold text-black mb-2">Mutare</h3>
          <Card className="bg-white border-yellow-500 border-2 shadow-md">
            <CardContent className="p-4 space-y-2">
              <h4 className="text-lg font-bold text-black">EasternSun Power</h4>
              <p className="text-gray-700">Certified by FireFlies | 6 Years Experience</p>
              <p className="flex items-center gap-1 text-yellow-500">
                <Star size={16} /> 4.7/5 (105 ratings)
              </p>
              <Button className="bg-yellow-400 text-black hover:bg-yellow-500">View Profile</Button>
            </CardContent>
          </Card>
        </div>
      </section>

      {/* Testimonials Section */}
      <section className="bg-yellow-50 p-4 rounded-xl shadow-md">
        <h4 className="text-lg font-semibold text-black mb-2">What Homeowners Say</h4>
        <div className="space-y-2 text-sm text-gray-700">
          <p>“My home hasn’t had a power issue since using a FireFlies-certified installer!” – <strong>Mrs. Chipo, Bulawayo</strong></p>
          <p>“The checklist helped me avoid fake batteries. Thank you FireFlies!” – <strong>Brian, Chitungwiza</strong></p>
          <p>“I feel safe knowing a real professional installed my system.” – <strong>Tendai, Gweru</strong></p>
        </div>
        <details className="mt-2 text-sm text-yellow-600 cursor-pointer">
          <summary>Read More Reviews</summary>
          <ul className="list-disc pl-6 text-gray-700 mt-2">
            <li>“Installers were professional and neat. I recommend them.” – Lindiwe, Mutare</li>
            <li>“It’s the first time I felt like someone wasn’t trying to scam me.” – Admire, Masvingo</li>
          </ul>
        </details>
      </section>

      <section className="mt-12 space-y-4">
        <h2 className="text-2xl font-semibold text-black">Downloads & Visual Aids</h2>
        <Card className="bg-white border-yellow-500 border-2 shadow-md">
          <CardContent className="p-4 space-y-2 text-gray-800">
            <p>Access our curated safety materials to support clean, compliant battery installations:</p>
            <ul className="list-disc pl-5 space-y-1">
              <li>
                <a href="/downloads/sample-battery-install-checklist.pdf" className="text-yellow-600 hover:underline" download>
                  🔽 Sample Battery Installation Checklist (PDF Preview)
                </a>
              </li>
              <li>
                <a href="/downloads/sample-battery-diagram.png" className="text-yellow-600 hover:underline" download>
                  🔽 Sample Battery Setup Diagram (PNG Preview)
                </a>
              </li>
              <li>
                <a href="/downloads/battery-installation-checklist.pdf" className="text-yellow-600 hover:underline" download>
                  🔽 Download Battery Installation Safety Checklist (PDF)
                </a>
              </li>
              <li>
                <a href="/downloads/battery-ventilation-guide.png" className="text-yellow-600 hover:underline" download>
                  🔽 Download Battery Ventilation Diagram (Image)
                </a>
              </li>
            </ul>
            <p>More diagrams and training videos coming soon through FireFlies Academy.</p>
          </CardContent>
        </Card>
        <h2 className="text-2xl font-semibold text-black">Safety First: Battery Installation Protocols</h2>
        <Card className="bg-white border-yellow-500 border-2 shadow-md">
          <CardContent className="p-4 space-y-2 text-gray-800">
            <p><strong>Proper battery installation is critical to prevent fire risks, system failures, and injury.</strong></p>
            <ul className="list-disc pl-5 space-y-1">
              <li>Always use certified lithium batteries from trusted suppliers.</li>
              <li>Install batteries in well-ventilated areas away from direct sunlight and flammable materials.</li>
              <li>Follow manufacturer torque settings for terminal connections to avoid loose or overtightened fittings.</li>
              <li>Include surge protection and appropriate fusing as per system specs.</li>
              <li>Ensure installers are trained in electrical safety and aware of local compliance guidelines (ZERA, SANS).</li>
            </ul>
            <p>FireFlies-certified workshops teach correct installation, maintenance, and troubleshooting—empowering safer solar homes.</p>
          </CardContent>
        </Card>
      </section>

      <footer className="text-center mt-12 text-black">
        <p>© 2025 FireFlies Solar Portal. Powering Safely. Empowering Communities.</p>
      </footer>
    </div>
  );
}

