[emergency-plumbing-landing-page-final.tsx](https://github.com/user-attachments/files/26915992/emergency-plumbing-landing-page-final.tsx)
import React from "react";

// =========================
// SIMPLE UI COMPONENTS (no external deps)
// =========================
const Button = ({ children, className = "", ...props }: any) => (
  <button
    className={`px-6 py-3 rounded-lg font-semibold ${className}`}
    {...props}
  >
    {children}
  </button>
);

const Card = ({ children }: any) => (
  <div className="border rounded-lg shadow-sm bg-white">{children}</div>
);

// =========================
// SHARED LAYOUT
// =========================
export function Layout({ children }: { children: React.ReactNode }) {
  return (
    <div className="min-h-screen flex flex-col bg-gray-50 text-gray-900">
      <header className="bg-white border-b px-6 py-4 flex justify-between items-center">
        <h1 className="text-xl font-bold">Emergency Plumbing</h1>

        <div className="text-right text-sm">
          <a href="tel:9546839341" className="block font-semibold text-blue-600">
            954-683-9341
          </a>
          <a href="tel:9545050846" className="block font-semibold text-blue-600">
            954-505-0846
          </a>
        </div>
      </header>

      <main className="flex-grow">{children}</main>

      <footer className="bg-gray-900 text-white py-6 text-center text-sm">
        © {new Date().getFullYear()} Emergency Plumbing • North Miami
      </footer>

      <a
        href="tel:9546839341"
        className="fixed bottom-4 left-4 right-4 bg-blue-600 text-white text-center py-4 rounded-xl md:hidden"
      >
        📞 Call Now
      </a>
    </div>
  );
}

// =========================
// LANDING PAGE
// =========================
export default function LandingPage() {
  return (
    <Layout>
      <section className="bg-blue-600 text-white py-20 px-6 text-center">
        <h1 className="text-4xl font-bold mb-4">
          24/7 Emergency Plumber Near You
        </h1>
        <p className="mb-6">
          Fast plumbing service in North Miami, Biscayne Park, Aventura & Miami Beach
        </p>

        <div className="flex flex-col md:flex-row justify-center gap-4">
          <a href="tel:9546839341">
            <Button className="bg-white text-blue-600">Call 954-683-9341</Button>
          </a>
          <a href="tel:9545050846">
            <Button className="bg-gray-200 text-black">Call 954-505-0846</Button>
          </a>
        </div>
      </section>
    </Layout>
  );
}
