---
title: "Appendix A: Martyrs"
authors:
    - name: Eric Araujo
date: 2025-10-20
---

The table below show a (non-exhaustive) list of notable Christian martyrs from the early church period, along with the approximate dates of their martyrdom, the Roman emperors during whose reigns they were martyred, and the estimated number of martyrs where applicable.

| Date | Emperor | Event/Location | Names of Notable Martyrs | Estimated Number |
|------|---|---|---|---|
| ~34 AD | Tiberius | Jerusalem | Stephen | 1 |
| ~43-45 AD | Claudius | Jerusalem | James the Greater (apostle) | 1 |
| ~54 AD | Nero | Hieropolis (Turkey) | Philip the Apostle | 1 |
| ~60 AD | Nero | Ethiopia | Matthew the Apostle | 1 |
| 64-68 AD | Nero | Rome | Nero's Persecution: Peter, Paul (apostles), and numerous Christians | 100s |
| ~68 AD | Nero | Alexandria | Mark the Apostle | 1 |
| ~72 AD | Vespasian | Jerusalem/Edessa | Jude (Thaddeus) and Simon the Zealot (apostles) | 2 |
| ~72 AD | Vespasian | India | Thomas the Apostle | 1 |
| 81-96 AD | Domitian | Roman Empire | Domitian's Persecution: various Christians throughout empire | 100s+ |
| ~95 AD | Domitian | Patmos/Ephesus | John the Apostle (exile; traditionally) | 1 |
| ~107-110 AD | Trajan | Rome | Ignatius of Antioch | 1 |
| ~155 AD | Antoninus Pius | Smyrna | Polycarp | 1 |
| ~165 AD | Marcus Aurelius | Rome | Justin Martyr and 6 companions | 7 |
| 177 AD | Marcus Aurelius | Lyon (Gaul) | Blandina, Pothinus, and others | 48+ |
| ~203 AD | Septimius Severus | Carthage (North Africa) | Perpetua, Felicity, and 3 companions | 5 |
| ~250 AD | Decius | Roman Empire | Various martyrs under Decius persecution | 100s |
| ~258 AD | Valerian | Rome/Carthage | Sixtus II, Lawrence, Cyprian | 3 |
| 303-311 AD | Diocletian | Roman Empire | Great Persecution under Diocletian (various locations) | 1000s |
| ~303 AD | Diocletian | Nicomedia | George (traditional) | 1 |
| ~304 AD | Diocletian | Alexandria | Catherine (traditional) | 1 |
| ~306 AD | Diocletian | Egypt | Sebastian (traditional) | 1 |
| 313 AD | Constantine | Roman Empire | Edict of Milan—persecution officially ends | 0 |
| ~335 AD | Constantine II | Persian Empire | Shapur II's Persecution: various Christians | 100s |
| ~380 AD | Theodosius I | Roman Empire | Christianity becomes official religion | 0 |
| 451 AD | Theodosius II | Armenia | Vardan Mamikonian and Armenian Christians (Battle of Avarayr) | 100s+ |

**Notes:**

- Dates marked with ~ are approximate, as exact dates are often uncertain
- Names in parentheses marked "traditional" indicate figures whose historicity is debated by scholars
- Numbers for mass persecutions are estimates based on historical records and church tradition
- By the 5th century, persecution had largely ended in the Roman Empire following Constantine's legalization of Christianity
- The Battle of Avarayr (451 AD) is one of the last recorded large-scale Christian persecutions in antiquity
- This table includes only major or well-documented martyrdoms; many others are recorded in various sources

import { BarChart, Bar, XAxis, YAxis, CartesianGrid, Tooltip, Legend, ResponsiveContainer, LineChart, Line } from 'recharts';
import { useState } from 'react';

export default function MartyrdomsChart() {
  const [chartType, setChartType] = useState('bar');

  const data = [
    { year: 34, deaths: 1, event: 'Stephen' },
    { year: 43, deaths: 1, event: 'James the Greater' },
    { year: 54, deaths: 1, event: 'Philip the Apostle' },
    { year: 60, deaths: 1, event: 'Matthew the Apostle' },
    { year: 64, deaths: 100, event: 'Nero\'s Persecution' },
    { year: 68, deaths: 1, event: 'Mark the Apostle' },
    { year: 72, deaths: 3, event: 'Jude, Simon, Thomas (apostles)' },
    { year: 81, deaths: 100, event: 'Domitian\'s Persecution' },
    { year: 95, deaths: 1, event: 'John (exile)' },
    { year: 107, deaths: 1, event: 'Ignatius' },
    { year: 155, deaths: 1, event: 'Polycarp' },
    { year: 165, deaths: 7, event: 'Justin Martyr' },
    { year: 177, deaths: 48, event: 'Lyon Persecution' },
    { year: 203, deaths: 5, event: 'Perpetua & Felicity' },
    { year: 250, deaths: 100, event: 'Decius Persecution' },
    { year: 258, deaths: 3, event: 'Sixtus II & Lawrence' },
    { year: 303, deaths: 1000, event: 'Diocletian Persecution' },
    { year: 313, deaths: 0, event: 'Edict of Milan (end)' },
    { year: 335, deaths: 100, event: 'Shapur II\'s Persecution' },
    { year: 451, deaths: 100, event: 'Battle of Avarayr (Armenia)' }
  ];

  return (
    <div className="w-full h-full p-8 bg-gradient-to-br from-slate-50 to-slate-100">
      <div className="bg-white rounded-lg shadow-lg p-6">
        <div className="mb-6">
          <h1 className="text-2xl font-bold mb-2 text-slate-800">Early Church Martyrdoms (1st-5th Centuries)</h1>
          <p className="text-slate-600 mb-4">Estimated number of deaths by year</p>
          
          <div className="flex gap-4">
            <button
              onClick={() => setChartType('bar')}
              className={`px-4 py-2 rounded font-medium transition ${
                chartType === 'bar'
                  ? 'bg-blue-500 text-white'
                  : 'bg-slate-200 text-slate-800 hover:bg-slate-300'
              }`}
            >
              Bar Chart
            </button>
            <button
              onClick={() => setChartType('line')}
              className={`px-4 py-2 rounded font-medium transition ${
                chartType === 'line'
                  ? 'bg-blue-500 text-white'
                  : 'bg-slate-200 text-slate-800 hover:bg-slate-300'
              }`}
            >
              Line Chart
            </button>
          </div>
        </div>
        
        <ResponsiveContainer width="100%" height={450}>
          {chartType === 'bar' ? (
            <BarChart data={data} margin={{ top: 20, right: 30, left: 0, bottom: 100 }}>
              <CartesianGrid strokeDasharray="3 3" />
              <XAxis 
                dataKey="year" 
                angle={-45}
                textAnchor="end"
                height={120}
                label={{ value: 'Year (AD)', position: 'insideBottomRight', offset: -20 }}
              />
              <YAxis 
                label={{ value: 'Number of Deaths', angle: -90, position: 'insideLeft' }}
              />
              <Tooltip 
                cursor={{ fill: 'rgba(59, 130, 246, 0.1)' }}
                content={({ active, payload }) => {
                  if (active && payload && payload.length) {
                    return (
                      <div className="bg-white p-3 border border-slate-300 rounded shadow-lg">
                        <p className="font-semibold text-slate-800">{payload[0].payload.event}</p>
                        <p className="text-slate-600">Year: {payload[0].payload.year} AD</p>
                        <p className="text-slate-600">Deaths: {payload[0].value}</p>
                      </div>
                    );
                  }
                  return null;
                }}
              />
              <Bar dataKey="deaths" fill="#3b82f6" radius={[8, 8, 0, 0]} />
            </BarChart>
          ) : (
            <LineChart data={data} margin={{ top: 20, right: 30, left: 0, bottom: 100 }}>
              <CartesianGrid strokeDasharray="3 3" />
              <XAxis 
                dataKey="year" 
                angle={-45}
                textAnchor="end"
                height={120}
                label={{ value: 'Year (AD)', position: 'insideBottomRight', offset: -20 }}
              />
              <YAxis 
                label={{ value: 'Number of Deaths', angle: -90, position: 'insideLeft' }}
              />
              <Tooltip 
                cursor={{ stroke: 'rgba(59, 130, 246, 0.5)' }}
                content={({ active, payload }) => {
                  if (active && payload && payload.length) {
                    return (
                      <div className="bg-white p-3 border border-slate-300 rounded shadow-lg">
                        <p className="font-semibold text-slate-800">{payload[0].payload.event}</p>
                        <p className="text-slate-600">Year: {payload[0].payload.year} AD</p>
                        <p className="text-slate-600">Deaths: {payload[0].value}</p>
                      </div>
                    );
                  }
                  return null;
                }}
              />
              <Line 
                type="monotone" 
                dataKey="deaths" 
                stroke="#3b82f6" 
                dot={{ fill: '#3b82f6', r: 4 }}
                activeDot={{ r: 6 }}
                strokeWidth={2}
              />
            </LineChart>
          )}
        </ResponsiveContainer>

        <div className="mt-8 p-4 bg-slate-50 rounded-lg border border-slate-200">
          <h2 className="font-semibold text-slate-800 mb-3">Key Observations:</h2>
          <ul className="text-sm text-slate-700 space-y-2">
            <li>• <strong>Early apostolic period (1st century):</strong> Individual martyrdoms of apostles, sporadic persecution</li>
            <li>• <strong>Nero's persecution (64-68 AD):</strong> First official Roman persecution, significant increase in deaths</li>
            <li>• <strong>2nd-3rd centuries:</strong> Intermittent persecutions under various emperors, relatively lower death tolls</li>
            <li>• <strong>Diocletian's Great Persecution (303-311 AD):</strong> Deadliest period in early church history, thousands of martyrs</li>
            <li>• <strong>Constantine & after (313+ AD):</strong> Christianity legalized; persecution in Roman Empire ends, but continues in Persian territories</li>
            <li>• <strong>5th century:</strong> Rare exceptions like Armenia (451 AD), but largely no systemic persecution in formerly pagan lands</li>
          </ul>
        </div>
      </div>
    </div>
  );
}