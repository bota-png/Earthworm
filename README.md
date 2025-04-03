import { useState } from 'react';
import { Button } from "@/components/ui/button"
import { Card, CardContent } from "@/components/ui/card"

export default function InvertebrateLab() {
  const [cut, setCut] = useState(false);
  const [testScore, setTestScore] = useState(null);

  const handleDissection = () => {
    setCut(true);
  };

  const handleTestSubmit = () => {
    // Simple logic for demonstration
    setTestScore("Your score: 4/5");
  };

  return (
    <div className="p-6 space-y-6">
      <h1 className="text-3xl font-bold">Virtual Invertebrate Lab: Earthworm</h1>

  {/* Context Section */}
      <Card>
        <CardContent className="p-4">
          <h2 className="text-xl font-semibold">Context</h2>
          <p>
            In this lab, students will virtually dissect an earthworm to explore its internal anatomy,
            following standard safety protocols. This module is part of the Organic Diversity unit.
          </p>
        </CardContent>
      </Card>

  {/* Protocol Section */}
      <Card>
        <CardContent className="p-4">
          <h2 className="text-xl font-semibold">Protocol</h2>
          <ol className="list-decimal pl-4">
            <li>Read the lab safety instructions carefully.</li>
            <li>Start the dissection simulation by clicking the button below.</li>
            <li>Explore the internal anatomy by hovering over parts.</li>
            <li>Take notes during the lab in the worksheet provided.</li>
            <li>Complete the quiz at the end to test your knowledge.</li>
          </ol>
        </CardContent>
      </Card>

  {/* Dissection Area */}
      <Card>
        <CardContent className="p-4">
          <h2 className="text-xl font-semibold">Dissection Simulation</h2>
          {!cut ? (
            <Button onClick={handleDissection}>Start Dissection</Button>
          ) : (
            <div className="mt-4">
              <p><strong>Earthworm Internal Anatomy:</strong></p>
              <ul className="list-disc pl-4">
                <li>Pharynx</li>
                <li>Esophagus</li>
                <li>Crop</li>
                <li>Gizzard</li>
                <li>Intestine</li>
                <li>Clitellum</li>
              </ul>
            </div>
          )}
        </CardContent>
      </Card>

  {/* Notes & Worksheet */}
      <Card>
        <CardContent className="p-4">
          <h2 className="text-xl font-semibold">Student Notes</h2>
          <p>Write down your observations here or use the worksheet provided by your teacher.</p>
          <a className="text-blue-600 underline" href="/worksheets/earthworm-lab.pdf" target="_blank">Download Worksheet (PDF)</a>
        </CardContent>
      </Card>

   {/* Result Section */}
      <Card>
        <CardContent className="p-4">
          <h2 className="text-xl font-semibold">Results</h2>
          <p>Summarize what you learned from the earthworm dissection.</p>
          <textarea className="w-full border p-2 mt-2 rounded" placeholder="Enter your conclusion here..." rows={4}></textarea>
        </CardContent>
      </Card>

   {/* Test Section */}
      <Card>
        <CardContent className="p-4">
          <h2 className="text-xl font-semibold">Lab Quiz</h2>
          <p>1. What organ grinds the food in an earthworm?</p>
          <p>a) Esophagus &nbsp;&nbsp; b) Gizzard &nbsp;&nbsp; c) Crop</p>
          <Button onClick={handleTestSubmit} className="mt-2">Submit Answer</Button>
          {testScore && <p className="mt-2 font-medium">{testScore}</p>}
        </CardContent>
      </Card>
    </div>
  );
}

